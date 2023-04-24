import telebot
#import requests
#import json

TOKEN = '6164420716:AAF8rmq6vROOo_LWRTngyU2fuzGW9DZBCdE'
bot = telebot.TeleBot (TOKEN)

posts = {
    'Директор':'350.000',
    'Менеджер':'195.000',
    'Специалист':'100.000',
    'Начинающий':'70.000',
}


@bot.message_handler(commands=['start', 'help'])
def help(message: telebot.types.Message):
    text = 'Чтобы начать работу с ботом введите команду в следующем формате: \n \
        <должность - из списка - > /positions \n \
        <стаж работы - лет>'
    bot.reply_to(message, text)


@bot.message_handler(commands=['author'])
def author(message: telebot.types.Message):
    text = 'Чатик создан Дмитрием Любо'
    bot.reply_to(message, text)


@bot.message_handler(commands=['positions'])
def positions(message: telebot.types.Message):
    text = 'Варианты должностей:'
    for i in posts.keys():
        text = '\n'.join((posts))
    bot.reply_to(message, text)


@bot.message_handler(content_types=['text'])
def comparison(message: telebot.types.Message):
    person_request = message.text.split(' ')
    if len(person_request) != 2:
        exit()
    position = person_request[0]
    bot.reply_to(message, f'Ваша оптимальная заработная плата на уровне {posts[position]} рублей')

@bot.message_handler()
def echo_test(message: telebot.types.Message):
    bot.send_message(message.chat.id, 'Привет, человек, хочешь узнать свою справедливую зарплату?')
    
bot.polling()
