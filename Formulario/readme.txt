var btn = document.getElementById('calc-btn')
        var capitulos = ['AESS', 'SPS', 'CIS', 'CSS', 'COMSOC', 'RAS', 'EDS', 'CAS', 'EMB', 'PES', 'IAS', 'GRSS', 'COMPUTER']


        function shuffle(a) {
            for (let i = a.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [a[i], a[j]] = [a[j], a[i]];
            }
            return a;
        }

        function showCalc() {
            var pertenencia = []
            var suma = 0
            for (var i = 0; i < 13; i++) {
                pertenencia.push(parseInt(Math.random() * 100))
                suma += pertenencia[i]
            }

            for (var i = 0; i < 13; i++) {
                pertenencia[i] = parseFloat((pertenencia[i]).toFixed(1))
            }
            pertenencia.sort(function (a, b) { return b - a })
            shuffle(capitulos)
            for (var i = 0; i < 13; i++) {
                card = `
            <h3>`+ capitulos[i] + `: ` + pertenencia[i] + `%</h3>
            `
                document.getElementById('show-calc').insertAdjacentHTML('beforeend', card);
            }
            console.log(pertenencia)
            btn.disabled = true;
            return false

        }