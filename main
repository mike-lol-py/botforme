



import pyTelegramBotAPI
import telebot
import pyowm
from pyowm.utils.config import get_default_config
#from pyowm import OWM
config_dict = get_default_config()
config_dict['language'] = 'ru'


keyboard1 = telebot.types.ReplyKeyboardMarkup()
keyboard1.row('Погода', 'Послать нахуй', 'Создатель бота')
owm = pyowm.OWM('5d5dd31dcdee4f30b7a7cbad01030c69')
bot = telebot.TeleBot('1250197049:AAHNXeGJSPqdn_XZkqT-_dr82oSVCzHm6gI')


@bot.message_handler(commands=['start'])
def start_message(message):
   bot.send_message(message.chat.id, 'Привет, мои возможности написаны на плитках ^-^', reply_markup=keyboard1)

#@bot.message_handler(content_types=['text'])
#def send_message(message):
#    if message.text == 'Создатель бота':
#        bot.send_massage(massage.caht.id, 'Вот он: https://vk.com/mixxxxail')


@bot.message_handler(content_types=['text'])
def send_message(message):
    if message.text == 'Послать нахуй':
        bot.send_message(message.chat.id, 'Иди нахуй')
    elif message.text == 'Погода':
        mgr =  owm.weather_manager()
        observation =  mgr.weather_at_place('Moscow')
        w =  observation.weather
        temp = w.temperature('celsius')["temp"]
        wind = w.wind()["speed"]
        bot.send_message(message.chat.id, "В Москве сейчас: \n" + w.detailed_status + " [" + str((int(temp))) + "°""]" + ",\nа также ветер: " + str(int(wind)) + "м/с.\nУдачного дня!")
    else: "Не понял, используй плиточки ^-^"

























#@bot.message_handler(content_types=['text'])
#def send_text(message):
#    if message.text == 'Послать нахуй':
#        bot.send_message(message.chat.id, "Иди нахуй))" )





# @bot.message_handler(commands=['start'])
# def start_message(message):
#    bot.send_message(message.chat.id, 'Привет, вот погода: ' + w)

#@bot.message_handler(content_types=['text'])
#def send_text(message):
#    if message.text == 'Привет':
#        bot.send_message(message.chat.id, 'Привет, мой создатель')
#    elif message.text == 'Пока':
#        bot.send_message(message.chat.id, 'Прощай, создатель')
#@bot.message_handler(commands=['help'])
#def start_message(message):
#   bot.send_message(message.chat.id, 'Узнать погоду - /weather')





#@bot.message_handler(content_types=['хуй'])
# def lalala(message):
#   bot.send_message(message.chat.id, message.text)

#RUN

bot.polling(none_stop = True)
