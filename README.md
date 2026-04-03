from kivy.app import App
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.button import Button
from kivy.uix.label import Label
import random

class RandomNumberApp(App):
    def build(self):
        self.layout = BoxLayout(orientation='vertical', padding=20, spacing=20)
        
        # Label — raqam ko‘rsatiladi
        self.label = Label(text="Boshing!", font_size=50)
        self.layout.add_widget(self.label)
        
        # Button — random raqam chiqaradi
        self.button = Button(text="Random raqam", font_size=30)
        self.button.bind(on_press=self.show_random_number)
        self.layout.add_widget(self.button)
        
        return self.layout
    
    def show_random_number(self, instance):
        number = random.randint(1, 10)
        self.label.text = str(number)

# Ilovani ishga tushirish
if __name__ == '__main__':
    RandomNumberApp().run()
