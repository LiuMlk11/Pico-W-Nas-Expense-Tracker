# Pico-W-Nas-Expense-Tracker
Basically a Network expense tracker using a pi pico W and a decade old NAS pc.
Pico W → NAS Expense Tracker
Pico W sends expense data to a NAS server over WiFi.
Setup

Pico W
    
Download pico_w_server.py
Change WiFi: YOUR_WIFI_NAME and YOUR_WIFI_PASSWORD
Open Thonny, paste code, run 
make sure you saved it into the pi pico.

ssh (your nas username)@YOUR_NAS_IP
nano nas_receiver.py
paste code, save (Ctrl+X, Y, Enter)
python3 nas_receiver.py

Test it by running :
curl -X POST http://your_pico_ip:8000/ -d "amount=50&category=food"

ssh (your nas username)@YOUR_NAS_IP
cat /mnt/storage/expenses.txt

I still have plans for this project so updates will be coming soon.
First and Final upgrade for this project, i was able to add a prediction system that would predict how much your spending would be for next month. As long as you logging in your purchases daily into the pi pico w. 

To add this feature, run :
nano analyze_expenses.py in any terminals.
then copy paste 
