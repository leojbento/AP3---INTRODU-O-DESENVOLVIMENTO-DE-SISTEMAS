# AP3---INTRODU-O-DESENVOLVIMENTO-DE-SISTEMAS
import PySimpleGUI as sg
score = 0

answers = ["1", "4", "2", "4", "3", "1", "1", "1", "1", "2"]

sg.theme('DarkAmber')   # Add a touch of color
# All the stuff inside your window.


layout =    [[sg.Text('BEM VINDO AO COVIQUIZ!')],
            [sg.Text('DIGITE SEU NOME:'), sg.InputText()],


    [sg.Text("""1) Como o COVID-19 é transmitido?
1. Através de gotículas que saem de sua boca e nariz quando você tosse ou expira 
2. Bebendo água impura 
3. Contato com animais 
4. Todas as alternativas""")],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""2) Quais são os sintomas comuns de COVID-19?
1. Uma tosse nova e contínua
2. Febre
3. Cansaço
4. Todas as alternativas""")] ,
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""3) Para qual das seguintes pessoas o COVID-19 é mais perigoso?
1. Idosos - especialmente aqueles com 70 anos ou mais
2. Pessoas com certas condições de saúde subjacentes
3. Crianças
4. Povo indígena""")],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""4) Os vírus que infectam bactérias são chamados?
1. Metanógenos
2. Patógenos
3. Fungos
4. Bacteriófagos""")],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""5)De onde veio o nome coronavírus?
1. Uma pessoa chamada Corona o identificou
2. Devido às projeções em forma de folha
3. Devido às suas projeções em forma de coroa
4. Nenhuma alternativa""")],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""6) Quanto tempo dura o período de incubação do COVID-19?
1. 1-14 dia
2. 5-25 dias
3. 10-15 dias
4. 40-50 dias""")
],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""7) Pessoas que não mostram sinais de uma determinada doença são;
1. Assintomático
2. Antipático
3. Diabetico
4. Nenhuma alternativa""")
],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""8) Ao contrario do COVID-19, que afeta predominantemente pessoas mais velhas que a gripe espanhola 
tem como alvo principal?
1. Jovens adultos
2. Sò mulheres
3. Crianças
4. Bebês""")
],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""9) Quanto tempo o vírus pode sobreviver em superfícies de plástico e aço inoxidável, de acordo com estudos?
1. 72 horas ou mais
2. 24 a 60 horas
3. 4 a 12 horas
4. 1 a 2 horas""")],

            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

 [sg.Text("""10) Qual é a temperatura corporal normal de um ser humano?
1. 35 - 36°C
2. 36 - 37°C
3. 37 - 38°C
4. 38 - 39°C""")],
            [sg.Text('SUA RESPOSTA É:'), sg.InputText()],

            [sg.Button('Ok'), sg.Button('Cancel')] ]

def answer(response):

    score = 0
    for index, a in enumerate(answers):

        if response[index+1] == a:
            score = score+1
    print(score)

    sg.Popup(response[0] + ", sua pontuação é:" + str(score), keep_on_top=True)



# Create the Window
# window = sg.Window('COVIQUIZ', layout , size = (800,900) )
window = sg.Window('COVIQUIZ').Layout([[sg.Column(layout, size=(800,900), scrollable=True)]])
# form.Read()
# Event Loop to process "events" and get the "values" of the inputs
while True:
    event, values = window.read()
    if event == 'Ok':

        answer(values)

    if event == sg.WIN_CLOSED or event == 'Cancel': # if user closes window or clicks cancel
        break
    print('You entered ', values[0])

window.close()
