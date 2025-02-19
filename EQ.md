# EQチューニング方法(音質を調整したい方向けの情報)
sink-eq6.confファイルをメモ帳などで開いてパラメータを編集します。  
基本的にいじる箇所はcontrol = { "Freq" = 100.0 "Q" = 1.0 "Gain" = 0.0 }のような箇所になります。  
パラメータの変更後はOSを再起動するか、ゲームを終了した状態で`systemctl restart pipewire`コマンドを実行すると設定が反映されます。  

[Freq]  
変化させる周波数(Hz)です。  
(Freqを0にしてGainを上げるとプリアンプのような働きになります。)  

[Q]  
Freqで設定した周波数を中心に前後どれくらいの周波数を巻き込んで変化させるかの値です。  
Q値が高いほど影響を受ける帯域幅は狭くなります。  
例えばQ値を4.3などにすると帯域幅は非常に狭くなるため、不自然に聞こえる可能性があります。  
(Q値を高くしてGainを下げることで特定の周波数をピンポイントで減らし、ノイズフィルターのような感じにも使えます)  
0.6から1.0の間のかなり穏やかな値で設定すると良い感じになります。  

[Gain]  
増幅値で-10〜20までの間で設定します。  

以上  

---

# How to tune EQ (information for those who want to adjust the sound quality)  
Open the sink-eq6.conf file in Notepad or similar and edit the parameters.  
Basically, the parts you need to tweak are things like control = { "Freq" = 100.0 "Q" = 1.0 "Gain" = 0.0 }.  
After changing the parameters, restart the OS or exit the game and execute the `systemctl restart pipewire` command to reflect the settings.  

[Freq]  
The frequency (Hz) to change.  
(If you set Freq to 0 and increase Gain, it will work like a preamplifier.)  

[Q]  
This is the value that determines how much frequency around the frequency set by Freq will be involved and changed.  
The higher the Q value, the narrower the affected bandwidth.  
For example, if the Q value is set to 4.3, the bandwidth will be very narrow, which may sound unnatural.  
(By increasing the Q value and decreasing Gain, you can pinpoint and reduce specific frequencies, and use it like a noise filter.)  
Setting it to a fairly gentle value between 0.6 and 1.0 sounds good.  

[Gain]  
Set the amplification value between -10 and 20.  

The end  
