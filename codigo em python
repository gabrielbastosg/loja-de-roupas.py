def loja_de_roupas():        
    # Lista de roupas disponíveis (nome, preço, cores disponíveis)
    roupas = [   
        {"nome": "Camisa", "preco": 60, "cores": ["Branca", "Preta", "Azul"]},
        {"nome": "Calça comprida", "preco": 90, "cores": ["Preta", "Jeans","Moletom"]},
        {"nome": "Vestido longo", "preco": 100, "cores": ["Vermelho", "Azul", "Verde"]},
        {"nome": "Jaqueta de Couro", "preco": 200, "cores": ["Preta", "Marrom","Cinza"]},
        {"nome": "Tênis", "preco": 120, "cores": ["Branco", "Preto","Marrom"]},
        {"nome": "Kit de roupa de praia", "preco": 140, "cores": ["Amarelo", "Azul"]},
        {"nome": "Kit de inverno", "preco": 160, "cores": ["Cinza", "Preto","Azul Marinho"]}
    ]

    carrinho = []

    print("Bem-vindo à loja Cea!\n")
    print("Você pode escolher vários produtos de uma vez, separando-os por vírgula (ex: 1,2,4)")
    print("Digite 0 para finalizar a compra a qualquer momento.\n")

    while True:
        print("\nLista de produtos:")
        for i, roupa in enumerate(roupas):
            cores_disponiveis = ", ".join(roupa["cores"])
            print(f"{i + 1} - {roupa['nome']} - R$ {roupa['preco']} - Cores: {cores_disponiveis}")
        print("0 - Finalizar compra")  # Simulando o "botão"

        escolha = input("\nEscolha o número da roupa para adicionar ao carrinho: ")

        if escolha.strip() == '0':  # Finalizar
            break

        try:
            # Dividir a entrada por vírgula e converter para números
            indices = [int(x.strip()) - 1 for x in escolha.split(",")]
            adicionou = False

            for index in indices:
                if 0 <= index < len(roupas):
                    # Escolher cor
                    cores = roupas[index]["cores"]
                    print(f"\nCores disponíveis para {roupas[index]['nome']}: {', '.join(cores)}")
                    cor_escolhida = input("Escolha a cor: ").strip().capitalize()
                    if cor_escolhida not in cores:
                        print(f"Cor inválida! Produto {roupas[index]['nome']} não adicionado.")
                        continue

                    # Adicionar ao carrinho com cor
                    item_com_cor = {
                        "nome": roupas[index]['nome'],
                        "preco": roupas[index]['preco'],
                        "cor": cor_escolhida
                    }
                    carrinho.append(item_com_cor)
                    print(f"{roupas[index]['nome']} ({cor_escolhida}) adicionado ao carrinho!")
                    adicionou = True
                else:
                    print(f"Produto {index + 1} inválido!")

            if not adicionou:
                print("Nenhum produto válido foi adicionado.")
                
        except ValueError:
            print("Digite apenas números separados por vírgula.")

    # Finalizar compra
    if carrinho:
        total = sum(item["preco"] for item in carrinho)
        print("\nCarrinho de compras:")
        for item in carrinho:
            print(f"- {item['nome']} ({item['cor']}) - R$ {item['preco']}")
        print(f"\nTotal da compra: R$ {total}")
        print("Obrigado por comprar conosco! Volte sempre!")
    else:
        print("\nSeu carrinho está vazio. Volte sempre!")

# Executar a função principal
if __name__ == "__main__":
    loja_de_roupas()    
