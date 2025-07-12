

javascript
Copiar
Editar
$(document).ready(function () {
    $('#tempSlider').on('input', function () {
        $('#temperature').text($(this).val());
        $('#status').text('En espera');
    });

    $('#coolBtn').click(function () {
        let temp = parseInt($('#temperature').text());
        if (temp > 22) {
            $('#status').text('Enfriando...');
            let interval = setInterval(() => {
                temp--;
                $('#temperature').text(temp);
                if (temp <= 22) {
                    $('#status').text('Temperatura óptima alcanzada');
                    clearInterval(interval);
                }
            }, 500);
        } else {
            $('#status').text('La temperatura ya es óptima');
        }
    });
});
*/
