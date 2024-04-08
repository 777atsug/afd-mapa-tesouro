class MapaTesouro:
    def __init__(self):
        # Define os estados possíveis do mapa do tesouro
        self.estados = {'Praia', 'Floresta', 'Caverna', 'Montanha', 'Ruínas', 'Tesouro'}
        # Define as transições possíveis entre os estados, representadas por pistas "A" e "B"
        self.transicoes = {
            'Praia': {'A': 'Floresta', 'B': 'Montanha'},
            'Floresta': {'A': 'Praia', 'B': 'Caverna'},
            'Caverna': {'A': 'Floresta', 'B': 'Ruínas'},
            'Montanha': {'A': 'Praia', 'B': 'Caverna'},
            'Ruínas': {'A': 'Caverna', 'B': 'Tesouro'}
        }
        # Define as dicas para cada estado e pista
        self.dicas = {
            'Praia': {'A': 'As árvores guardam o caminho.', 'B': 'As alturas revelam segredos.'},
            'Floresta': {'A': 'Retornar à origem pode revelar novos caminhos.', 'B': 'A escuridão esconde a verdade.'},
            'Caverna': {'A': 'A luz natural te guiará de volta.', 'B': 'Antigas construções sussurram histórias de tesouros.'},
            'Montanha': {'A': 'Onde a areia encontra o mar, um novo começo te espera.', 'B': 'Profundezas ocultas guardam segredos.'},
            'Ruínas': {'A': 'Os ecos do passado podem te confundir.', 'B': 'O final da jornada está próximo.'}
        }
        # Define o estado inicial e o estado final do mapa do tesouro
        self.estado_inicial = 'Praia'
        self.estado_final = 'Tesouro'

    def transitar(self, estado_atual, pista):
        # Verifica se o estado e a pista fornecidos levam a um próximo estado válido
        if estado_atual in self.transicoes and pista in self.transicoes[estado_atual]:
            return self.transicoes[estado_atual][pista]
        else:
            return None

    def obter_dica(self, estado_atual, pista):
        # Retorna a dica correspondente ao estado e pista fornecidos
        if estado_atual in self.dicas and pista in self.dicas[estado_atual]:
            return self.dicas[estado_atual][pista]
        else:
            return None


def testar_autômato():
    mapa = MapaTesouro()
    estado_atual = mapa.estado_inicial
    caminho = [estado_atual]  # Inicializa a lista para armazenar o caminho percorrido
    print(f"Começando na {estado_atual}")
    # Obtém a primeira pista com base no estado atual
    pista = input("Insira a pista encontrada (A ou B): ").upper()
    # Obtém a dica correspondente à primeira pista fornecida
    dica = mapa.obter_dica(estado_atual, pista)
    if dica:
        print(f"Dica: {dica}")
    # Loop enquanto o estado atual não for o estado final (Tesouro)
    while estado_atual != mapa.estado_final:
        # Obtém o próximo estado com base na pista fornecida
        proximo_estado = mapa.transitar(estado_atual, pista)
        if proximo_estado:
            print(f"Seguindo a pista '{pista}' para a {proximo_estado}")
            estado_atual = proximo_estado
            caminho.append(estado_atual)
        else:
            # Se a pista fornecida for inválida, solicita ao jogador que tente novamente
            print("Pista inválida. Tente novamente.")
        # Solicita ao jogador uma nova pista
        pista = input("Insira a próxima pista encontrada (A ou B): ").upper()
        # Obtém a dica correspondente à nova pista fornecida
        dica = mapa.obter_dica(estado_atual, pista)
        if dica:
            print(f"Dica: {dica}")

    # Imprime o caminho percorrido ao encontrar o tesouro
    print("Parabéns! Você encontrou o tesouro!")
    print("Caminho percorrido:")
    print(" -> ".join(caminho))


testar_autômato()
