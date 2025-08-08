https://github.com/naing8392/CryptoKoNaingBot/tree/main
import os
from datetime import datetime

TOKEN = os.getenv("BOT_TOKEN")
bot = telebot.TeleBot(TOKEN)

# Start Command
@bot.message_handler(commands=['start'])
def send_welcome(message):
    bot.reply_to(message, "မင်္ဂလာပါ ကိုနိုင် 😎\nCryptoKoNaingBot မှကြိုဆိုပါတယ်။\n\n/airdrop - weekly airdrop reminder\n/help - commands list")

# Help Command
@bot.message_handler(commands=['help'])
def send_help(message):
    bot.reply_to(message, "/start - start bot\n/airdrop - weekly reminder\n/help - commands list")

# Airdrop Command
@bot.message_handler(commands=['airdrop'])
def airdrop_reminder(message):
    bot.reply_to(message, "📅 Weekly Airdrop Reminder:\n1. Check Twitter & Discord tasks\n2. Claim daily check-ins\n3. Update wallet addresses")

# Fallback
@bot.message_handler(func=lambda m: True)
def echo_all(message):
    bot.reply_to(message, "မင်းရဲ့ command ကို မသိဘူးနော် 😅 /help လို့ ရိုက်ကြည့်ပါ")

bot.polling()start

