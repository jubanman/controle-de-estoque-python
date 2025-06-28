# 🧮 Controle de Estoque com Python / Gestion de Stock avec Python

Este projeto de terminal permite ao usuário gerenciar um estoque simples usando Python puro, ideal para treinar lógica de programação.

Ce projet en Python permet de gérer un petit stock via le terminal, parfait pour les débutants en programmation.

## ✨ Funcionalidades / Fonctionnalités
- Adicionar produtos / Ajouter des produits  
- Consultar quantidade / Consulter une quantité  
- Atualizar estoque / Mettre à jour le stock  
- Remover produtos / Supprimer des produits  
- Visualizar lista completa / Afficher tout le stock

## 🎯 Tecnologias / Technologies
- Python 3  
- Sem bibliotecas externas / Sans bibliothèques externes

## 🚀 Como usar / Comment exécuter

```bash
python estoque.py

# Controle de Estoque / Gestion de Stock
# Autor / Auteur : Julian Marchiori

estoque = {}

def exibir_menu():
    print("\n=== MENU ===")
    print("1. Adicionar produto / Ajouter un produit")
    print("2. Consultar produto / Consulter un produit")
    print("3. Atualizar quantidade / Mettre à jour la quantité")
    print("4. Remover produto / Supprimer un produit")
    print("5. Mostrar estoque / Afficher le stock")
    print("6. Sair / Quitter")

def adicionar_produto():
    nome = input("Nome do produto / Nom du produit: ")
    quantidade = int(input("Quantidade / Quantité: "))
    estoque[nome] = quantidade
    print(f"{nome} adicionado com {quantidade} unidade(s).")

def consultar_produto():
    nome = input("Nome do produto / Nom du produit: ")
    if nome in estoque:
        print(f"{nome} -> {estoque[nome]} unidade(s)")
    else:
        print("Produto não encontrado / Produit non trouvé.")

def atualizar_quantidade():
    nome = input("Nome do produto / Nom du produit: ")
    if nome in estoque:
        quantidade = int(input("Nova quantidade / Nouvelle quantité: "))
        estoque[nome] = quantidade
        print(f"{nome} atualizado para {quantidade} unidade(s).")
    else:
        print("Produto não encontrado / Produit non trouvé.")

def remover_produto():
    nome = input("Nome do produto / Nom du produit: ")
    if nome in estoque:
        del estoque[nome]
        print(f"{nome} removido.")
    else:
        print("Produto não encontrado / Produit non trouvé.")

def mostrar_estoque():
    print("\n=== Estoque Atual / Stock Actuel ===")
    if not estoque:
        print("Estoque vazio / Stock vide.")
    else:
        for produto, quantidade in estoque.items():
            print(f"{produto} : {quantidade} unidade(s)")

# Loop principal
while True:
    exibir_menu()
    escolha = input("Escolha uma opção / Choisissez une option: ")

    if escolha == '1':
        adicionar_produto()
    elif escolha == '2':
        consultar_produto()
    elif escolha == '3':
        atualizar_quantidade()
    elif escolha == '4':
        remover_produto()
    elif escolha == '5':
        mostrar_estoque()
    elif escolha == '6':
        print("Saindo... / Fermeture...")
        break
    else:
        print("Opção inválida / Option invalide.")
