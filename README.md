
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Headings</title>
    <style>
        h1, h2, h3 {
            margin: 20px;
            padding: 10px;
        }
        .yellow-text {
            color: yellow;
        }
        .black-text {
            color: black;
        }
        .green-text {
            color: green;
        }
        .yellow-bg {
            background-color: yellow;
        }
        .blue-bg {
            background-color: blue;
        }
    </style>


    <h1 id="h1-1">Heading 1 - 1</h1>
    <h1 id="h1-2">Heading 1 - 2</h1>
    <h2 id="h2-1">Heading 2 - 1</h2>
    <h2 id="h2-2">Heading 2 - 2</h3>
    <h3 id="h3-1">Heading 3 - 1</h3>

    <script>
        let h1Elements = document.querySelectorAll('h1');
        let h2Elements = document.querySelectorAll('h2');
        let h3Element = document.getElementById('h3-1');
        let disableH2Actions = false;

        h1Elements.forEach(element => {
            element.addEventListener('click', () => {
                element.classList.add('yellow-text');
            });
            element.addEventListener('mouseover', () => {
                element.classList.add('black-text');
                element.classList.remove('yellow-text', 'green-text');
            });
            element.addEventListener('mouseout', () => {
                element.classList.add('green-text');
                element.classList.remove('black-text');
            });
            element.addEventListener('mousedown', () => {
                element.classList.add('yellow-bg');
            });
            element.addEventListener('mouseup', () => {
                element.classList.remove('yellow-bg');
            });
        });

        h2Elements.forEach(element => {
            element.addEventListener('click', () => {
                if (!disableH2Actions) {
                    element.classList.add('yellow-text');
                }
            });
            element.addEventListener('mouseover', () => {
                if (!disableH2Actions) {
                    element.classList.add('black-text');
                    element.classList.remove('yellow-text', 'green-text');
                }
            });
            element.addEventListener('mouseout', () => {
                if (!disableH2Actions) {
                    element.classList.add('green-text');
                    element.classList.remove('black-text');
                }
            });
            element.addEventListener('mousedown', () => {
                if (!disableH2Actions) {
                    element.classList.add('blue-bg');
                }
            });
            element.addEventListener('mouseup', () => {
                if (!disableH2Actions) {
                    element.classList.remove('blue-bg');
                }
            });
        });

        h3Element.addEventListener('click', () => {
            disableH2Actions = true;
        });
    </script>
    
</body>
</html>

