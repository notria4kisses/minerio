# minerio
principio de matéria escura onde se sub existe

import geminipy
from nltk.chat.util import Chat, reflections

# Inicialização da API Gemini
api_key = "sua_api_key"
api_secret = "seu_api_secret"
client = geminipy.PrivateClient(api_key, api_secret)

# Padrões e respostas para o chatbot
patterns = [
    (r"oi|olá", ["Olá!", "Oi! Como posso ajudar?"]),
    (r"pedra preciosa opala", ["A opala é uma pedra preciosa conhecida por sua beleza única."]),
    (r"valor", ["O valor da opala pode variar dependendo da qualidade e do tamanho da pedra."]),
    (r"pagamento", ["Aceitamos pagamento via PIX, cartão e QR code."]),
    (r"PIX|pix", ["Você pode fazer um pagamento via PIX para a nossa chave: xxxxxxxxxx."]),
    (r"cartão", ["Aceitamos pagamentos com cartão de crédito e débito."]),
    (r"QR code", ["Você pode escanear nosso QR code para fazer um pagamento."]),
    (r"sair|adeus", ["Até mais!", "Volte sempre!"]),
]

# Criar o chatbot
chatbot = Chat(patterns, reflections)

# Função principal do chatbot
def main():
    print("Olá! Eu sou um chatbot que pode te fornecer informações sobre a opala e nossas formas de pagamento.")
    print("Digite 'sair' para sair do chat.")
    while True:
        user_input = input("Você: ").lower()
        response = chatbot.respond(user_input)
        if response:
            print("Chatbot:", response[0])
        else:
            print("Desculpe, eu não entendi. Você poderia repetir, por favor?")

if __name__ == "__main__":
    main()

