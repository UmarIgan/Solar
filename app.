from tkinter import *
from pysolar.solar import *
from math import acos, cos, sin, tan, degrees, pi, asin, radians, atan
import sys
import datetime

pencere=Tk()
pencere.geometry("550x700+400+150")
pencere.title("solar energy")
pencere.configure(bg='grey25')
new_dict={1: -23.04, 2: -22.59, 3: -22.54, 4: -22.48, 5: -22.42, 6: -22.36, 7: -22.28, 8: -44.34, 9: -22.05, 10: -21.56, 11: -21.47, 12: -21.37, 13: -21.27, 14: -21.16, 15: -21.06, 16: -20.54,
          17: -20.42, 18: -20.3, 19: -20.18, 20: -20.05, 21: -19.52, 22: -19.38, 23: -19.24, 24: -19.1, 25: -18.55, 26: -18.4, 27: -18.25, 28: -18.09, 29: -17.53, 30: -17.37, 31: -17.2, 32: -17.03,
          33: -16.46, 34: -16.25, 35: -16.1, 36: -15.52, 37: -15.34, 38: -15.15, 39: -14.56, 40: -14.37, 41: -14.18, 42: -13.58, 43: -13.38, 44: -13.18, 45: -12.58, 46: -12.37, 47: -12.16, 48: -11.55,
          49: -11.34, 50: -11.13, 51: -10.52, 52: -10.3, 53: -10.08, 54: -9.46, 55: -18.25, 56: -8.39, 57: -8.17, 58: -8.03, 59: -7.49, 60: -7.26, 61: -7.03, 62: -6.4, 63: -6.17, 64: -5.54,
          65: -5.3, 66: -5.07, 67: -4.44, 68: -4.2, 69: -3.57, 70: -3.33, 71: -3.1, 72: -2.46, 73: -2.22, 74: -1.59, 75: -1.35, 76: -1.11, 77: -0.48, 78: -0.2, 79: 0.0, 80: 0.24, 81: 0.47, 82: 1.11,
          83:1.35, 84: 1.58, 85: 2.22, 86: 2.45, 87: 3.09, 88: 3.32, 89: 3.55, 90: 4.18, 91: 4.42, 92: 5.05, 93: 5.28, 94: 5.51, 95: 6.13, 96: 6.36, 97: 6.59, 98: 7.21, 99: 7.43, 100: 8.07, 101: 8.28,
          102: 8.5, 103: 9.11, 104: 9.33, 105: 9.54, 106: 10.16, 107: 10.37, 108: 10.58, 109: 11.19, 110: 11.39, 111: 12.0, 112: 12.2, 113: 12.4, 114: 13.0, 115: 13.19, 116: 13.38, 117: 13.58, 118: 14.16,
          119: 14.35, 120: 14.54, 121: 15.12, 122: 15.3, 123: 15.47, 124: 16.04, 125: 16.22, 126: 16.39, 127: 16.55, 128: 17.12, 129: 17.27, 130: 17.43, 131: 17.59, 132: 18.14, 133: 18.29, 134: 18.43,
          135: 18.58, 136: 19.11, 137: 19.25, 138: 19.38, 139: 19.51, 140: 20.04, 141: 20.16, 142: 20.28, 143: 20.39, 144: 20.5, 145: 21.01, 146: 21.12, 147: 21.22, 148: 21.31, 149: 21.41, 150: 21.5,
          151: 21.58, 152: 22.06, 153: 22.14, 154: 22.22, 155: 22.2, 156: 22.35, 157: 22.42, 158: 22.47, 159: 22.53, 160: 22.58, 161: 23.02, 162: 23.07, 163: 23.11, 164: 23.14, 165: 23.17, 166: 23.2,
          167: 23.22, 168: 23.24, 169: 23.25, 170: 23.26, 171: 23.26, 172: 23.26, 173: 23.26, 174: 23.25, 175: 23.24, 176: 23.23, 177: 23.21, 178: 23.19, 179: 23.16, 180: 23.13, 181: 23.09, 182: 23.05,
          183: 23.01, 184: 22.56, 185: 22.51, 186: 22.45, 187: 22.39, 188: 22.33, 189: 22.26, 190: 22.19, 191: 22.11, 192: 22.04, 193: 21.55, 194: 21.46, 195: 21.37, 196: 21.28, 197: 21.18, 198: 21.08,
          199: 20.58, 200: 20.47, 201: 20.36, 202: 20.24, 203: 20.12, 204: 20.0, 205: 19.47, 206: 19.34, 207: 19.21, 208: 19.08, 209: 18.54, 210: 18.4, 211: 18.25, 212: 18.1, 213: 17.55, 214: 17.4,
          215: 17.24, 216: 17.08, 217: 16.52, 218: 16.36, 219: 16.19, 220: 16.02, 221: 15.45, 222: 15.27, 223: 15.1, 224: 14.52, 225: 14.33, 226: 14.15, 227: 13.56, 228: 13.37, 229: 13.18, 230: 12.59,
          231: 12.39, 232: 12.19, 233: 11.59, 234: 11.39, 235: 11.19, 236: 10.58, 237: 10.38, 238: 10.17, 239: 9.56, 240: 9.35, 241: 9.13, 242: 8.52, 243: 8.3, 244: 8.09, 245: 7.47, 246: 7.25, 247: 7.03,
          248: 6.4, 249: 6.18, 250: 5.56, 251: 5.33, 252: 5.1, 253: 4.48, 254: 4.25, 255: 4.02, 256: 3.39, 257: 3.16, 258: 2.53, 259: 2.3, 260: 2.06, 261: 1.43, 262: 1.2, 263: 0.57, 264: 0.33, 265: 0.1,
          266: -0.14, 267: -0.37, 268: -1.0, 269: -1.24, 270: -1.47, 271: -2.1, 272: -2.34, 273: -2.57, 274: -3.2, 275: -3.44, 276: -4.07, 277: -4.3, 278: -4.53, 279: -5.16, 280: -5.39, 281: -6.02,
          282: -6.25, 283: -6.48, 284: -7.1, 285: -7.32, 286: -7.55, 287: -8.18, 288: -8.4, 289: -9.02, 290: -9.24, 291: -9.45, 292: -10.07, 293: -10.29, 294: -10.5, 295: -11.12, 296: -11.33,
          297: -11.54, 298: -12.14, 299: -12.35, 300: -12.55, 301: -13.15, 302: -13.35, 303: -13.55, 304: -14.14, 305: -14.34, 306: -14.53, 307: -15.11, 308: -15.3, 309: -15.48, 310: -16.06, 311: -16.24,
          312: -16.41, 313: -16.58, 314: -17.15, 315: -17.32, 316: -17.48, 317: -18.04, 318: -18.2, 319: -18.35, 320: -18.5, 321: -19.05, 322: -19.19, 323: -19.33, 324: -19.47, 325: -20.0, 326: -20.13,
          327: -20.26, 328: -20.38, 329: -20.5, 330: -21.0, 331: -21.12, 332: -21.23, 333: -21.33, 334: -21.43, 335: -21.52, 336: -22.01, 337: -22.1, 338: -22.18, 339: -22.25, 340: -22.32, 341: -22.39,
          342: -22.46, 343: -22.52, 344: -22.57, 345: -23.02, 346: -23.07, 347: -23.11, 348: -23.14, 349: -23.17, 350: -23.2, 351: -23.22, 352: -23.24, 353: -23.25, 354: -23.26, 355: -23.26, 356: -23.26,
          357: -23.26, 358: -23.25, 359: -23.23, 360: -23.2, 361: -23.19, 362: -23.16, 363: -23.12, 364: -23.0, 365: -23.05}
def declination_angle():
    L=int(ent3.get())
    return_value=new_dict.get(L)
    blank2.insert(0,return_value)    
lbl4=Label(text="day of the yaer", bg="dark turquoise", font="Times 15  bold italic" )
lbl4.grid(row=0, column=0)
ent3=Entry(width=10)
ent3.grid(row=0, column=1)
btn2=Button(text="dec. angle",width=14, bg="dark turquoise" , font="Times 15  bold italic", command=declination_angle)
btn2.grid(row=1, column=0, padx=4, pady=4)
blank2=Entry(width=10)#dec angle
blank2.grid(row=1, column=1)
def hour_angle():
    n=float(Ent.get())
    w=15*(n-12)
    blan.insert(0, w)
bt=Button(text="input time:", width=14, bg="dark turquoise", font="Times 15  bold italic" , command=hour_angle)
bt.grid(row=5, column=0, padx=4, pady=4)
Ent=Entry(width=10)

Ent.grid(row=5, column=1)
lba=Label(text="hour angle: ", width=14 , font="Times 15  bold italic", bg="dark turquoise"  )
lba.grid(row=6, column=0, padx=4, pady=4)
blan=Entry(width=10)#hour angle
blan.grid(row=6, column=1)
def sunset_hour_angle():#sin(H) = - sin(A) cos(a) / cos(δ) 
    d=radians(float(blank2.get()))
    t=radians(float(ent4.get()))
    c=float(tan(t))
    b=float(tan(d))
    M=float((-b)*c)
    R=(degrees(acos(M)))
    blank3.insert(0, R)
 #latitude and longtitude degrees of turkey cities  
lat={'Adana': 36.9914, 'Adıyaman': 37.7639, 'Afyon': 38.7595, 'Ağri': 39, 'Aksaray': 38.3686, 'Amasya': 40.6565, 'Ankara': 39.9334, 'Antalya': 36.8969, 'Ardahan': 41.113, 'Artvin': 41.1809,
'Aydın': 37.838, 'Balıkesir': 39.6533, 'Bartın': 41.6377, 'Batman': 37.8888, 'Bayburt': 40.2603, 'Bilecik': 40.1426,  'Bingol': 38.8855, 'Bitlis': 38.4006, 'Bolu': 40.7325, 'Burdur': 37.7182, 'Bursa': 40.1885,
'Çanakkale': 40.1467, 'Çankırı': 40.6002, 'Çorum': 40.5499, 'Denizli': 37.783, 'Diyarbakır': 37.925, 'Düzce': 40.8387, 'Edirne': 41.6771, 'Elazığ': 38.6748, 'Erzincan': 39.7469, 'Erzurum': 39.9056,
'Eskişehir': 39.7667, 'Gaziantep': 37.066, 'Giresun': 40.9175, 'Gümüşhane': 40.4609, 'Hakkari': 37.5774, 'Hatay': 36.3524, 'Iğdır': 39.9191, 'Isparta': 37.7626, 'İstanbul': 41.0082, 'İzmir': 38.4237,
'Kahramanmaraş': 37.5753, 'Karabük': 41.1956, 'Karaman': 37.181, 'Kars': 40.6013, 'Kastamonu': 41.3766, 'Kayseri': 38.7205, 'Kilis': 36.7165, 'Kırıkkale': 39.8398, 'Kırklareli': 41.7355, 'Kırşehir': 39.1463,
'Kocaeli': 40.7655, 'Konya': 37.8746, 'Kütahya': 39.42, 'Malatya': 38.3556, 'Manisa': 38.614, 'Mardin': 37.3126, 'Mersin': 36.8121, 'Muğla': 37.2154, 'Muş': 38.7346, 'Nevşehir': 38.6247, 'Niğde': 37.9698,
'Ordu': 40.9862, 'Osmaniye': 37.0748, 'Rize': 41.0255, 'Sakarya': 40.7731, 'Samsun': 41.2797, 'Şanlıurfa': 37.1674, 'Siirt': 37.9274, 'Sinop': 42.028, 'Şırnak': 37.519,
'Sivas': 39.7505, 'Tekirdağ': 40.9781, 'Tokat': 40.3235, 'Trabzon': 41.0027, 'Tunceli': 39.1062, 'Uşak': 38.6742, 'Van': 38.5012, 'Yalova': 40.6549, 'Yozgat': 39.821, 'Zonguldak': 41.4535}

long={'Adana': 35.3308, 'Adıyaman': 38.2775, 'Afyon': 30.5387, 'Ağrı': 43.0506, 'Aksaray': 34.0297, 'Amasya': 35.8373, 'Ankara': 32.8597, 'Antalya': 30.7133, 'Ardahan': 42.7023,
      'Artvin':41.8208, 'Aydın': 27.8456, 'Balıkesir': 27.8903, 'Bartın':32.3338, 'Batman': 41.1285, 'Bayburt': 40.228, 'Bilecik': 29.9793, 'Bingol': 40.4966, 'Bitlis': 42.1095, 'Bolu': 31.6082,
      'Burdur': 30.2813, 'Bursa': 29.061, 'Çanakkale': 26.4086, 'Çankırı': 33.6162, 'Çorum': 34.9537, 'Denizli': 29.0963, 'Diyarbakır': 40.211, 'Düzce': 31.1626, 'Edirne': 26.5557,
      'Elazığ': 39.2225, 'Erzincan': 39.491, 'Erzurum': 41.2658, 'Eskişehir': 30.5256, 'Gaziantep': 37.3781, 'Giresun': 38.3927, 'Gümüşhane': 39.4804, 'Hakkari': 43.7368, 'Hatay':36.2935,
      'Iğdır': 44.0442, 'Isparta': 30.5537, 'İstanbul': 28.9784, 'İzmir': 27.1428, 'Kahramanmaraş':36.9228, 'Karabük': 32.6227, 'Karaman': 33.2222, 'Kars': 43.0975, 'Kastamonu': 33.7765,
      'Kayseri': 35.4826, 'Kilis': 37.1147, 'Kırıkkale': 33.5089, 'Kırklareli': 27.2245, 'Kırşehir': 34.1599, 'Kocaeli': 29.9407, 'Konya': 32.4932, 'Kütahya': 29.9857, 'Malatya': 38.3336,
      'Manisa': 27.4296, 'Mardin': 40.739, 'Mersin': 34.6415, 'Muğla': 28.3636, 'Muş': 41.491, 'Nevşehir': 34.7142, 'Niğde': 34.6766, 'Ordu': 37.8797, 'Osmaniye': 36.2466, 'Rize': 40.5177,
      'Sakarya': 30.3948, 'Samsun': 36.3361, 'Şanlıurfa': 38.7955, 'Siirt': 41.942, 'Sinop': 35.1517, 'Şırnak': 42.4537, 'Sivas': 37.015,
      'Tekirdağ': 27.5117, 'Tokat': 36.5522, 'Trabzon': 39.7168, 'Tunceli': 39.5483, 'Uşak': 29.4059, 'Van': 43.373, 'Yalova': 29.2842, 'Yozgat': 34.8086, 'Zonguldak': 31.7894}

def lati():#finding lat. degree
    L=ent7.get()
    r=lat.get(L)
    ent4.insert(0, r)
def longi():#finding long. degree
    L=ent7.get()
    r=long.get(L)
    ent41.insert(0, r)


Lat=Button(text="latitude: ", font="Times 15  bold italic" , width=14, bg="dark turquoise", command=lati)
Lat.grid(row=2, column=0,padx=4, pady=4)
ent4=Entry(width=10)
ent4.grid(row=2, column=1)
Long=Button(text="longtitude: ", font="Times 15  bold italic" , width=14, bg="dark turquoise", command=longi)
Long.grid(row=3, column=0)
ent41=Entry(width=10)
ent41.grid(row=3, column=1 )
btn3=Button(text="hs angle: ", width=14, font="Times 15  bold italic" , bg="dark turquoise",command=sunset_hour_angle)
btn3.grid(row=4, column=0, padx=4, pady=4)
blank3=Entry(width=10)#hs
blank3.grid(row=4, column=1)

def daylight_hour():
    H=float(blank3.get())
    N=int((2/15)*(H))
    bln5.insert(0, N)
    
btn5=Button(text="daylength: ", width=14 , font="Times 15  bold italic", bg="dark turquoise" , command=daylight_hour)
btn5.grid(row=7, column=0, padx=4, pady=4)
bln5=Entry(width=10)#daylight
bln5.grid(row=7, column=1)

def altitude():
    date=datetime.datetime.now()
    m=float(ent4.get())
    n=float(ent41.get())
    LA=get_altitude(m, n, date) 
    blank4.insert(0, LA)

btn4=Button(text="Altitude: ",width=14, font="Times 15  bold italic" , bg="dark turquoise", command=altitude)
btn4.grid(row=8, column=0, padx=4, pady=4)
blank4=Entry(width=10)#zenith
blank4.grid(row=8, column=1)

def Zenith():
    x=float(blank4.get())
    z=float(90-x)
    blank5.insert(0, z)
 
btn5=Button(text="Zenith: ", width=14, font="Times 15  bold italic" , bg="dark turquoise", command=Zenith)
btn5.grid(row=9, column=0, padx=4, pady=4)
blank5=Entry(width=10)#altitude
blank5.grid(row=9, column=1)

    
def Azimuth():
    date = datetime.datetime.now()
    m=float(ent4.get())
    n=float(ent41.get())
    A=float(get_azimuth(m, n, date))
    blank6.insert(0, A)        
btn6=Button(text="azimuth: ",width=14, font="Times 15  bold italic", bg="dark turquoise", command=Azimuth)
btn6.grid(row=10, column=0, padx=4, pady=4)
blank6=Entry(width=10)#azimuth
blank6.grid(row=10, column=1)

def sunrise():
    A=float(bln5.get())
    B=int(12-(A/2))
    S=float(B)-int(B)
    s=S*(60/100)
    B=float(int(B)+s)
    blank7.insert(0, B)
btn7=Button(text="sunset: ", width=14, font="Times 15  bold italic" , bg="dark turquoise", command=sunrise)
btn7.grid(row=11, column=0, padx=4, pady=4)
blank7=Entry(width=10)
blank7.grid(row=11, column=1)
def sunset():
    A=float(bln5.get())
    B=int(12+(A/2))
    blank8.insert (0, B)
btn8=Button(text="sunset: ", width=14 , font="Times 15  bold italic", bg="dark turquoise", command=sunset)
btn8.grid(row=12, column=0, padx=4, pady=4)
blank8=Entry(width=10)
blank8.grid(row=12, column=1)

def Radiation():#energy of given city
    date=datetime.datetime.now()
    A=float(blank4.get())
    m=radiation.get_radiation_direct(date, A)
    blank14.insert(0, m)
btn14=Button(text="radiation ", width=14, font="Times 15  bold italic" , bg="dark turquoise", command=Radiation)
btn14.grid(row=15, column=0)
blank14=Entry(width=10)
blank14.grid(row=15, column=1)

#daily radiation for cities of turkey
new_dicta={' Adana':1564,  'Adıyaman':1595, 'Afyonkarahisar':1557 , 'Ağrı':1570, 'Aksaray':1578, 'Amasya':1393, 'Ankara':1473, 'Antalya':1646, 'Ardahan':1472, 'Artvin':1409, 'Aydın':1557, 'Balıkesir':1418, 'Bartın':1307,'Batman':1576,
           ' Bayburt':1529, 'Bilecik':1412, 'Bingöl':1592, 'Bitlis':1604, 'Bolu':1416, 'Burdur':1631, 'Bursa':1393, 'Çanakkale':1375, 'Çankırı':1432, 'Çorum':1419, ' Denizli':1591,
           'Diyarbakır':1473, 'Düzce':1344, 'Edirne':1319, 'Elazığ':1588, 'Erzincan':1555, ' Erzurum':1393, ' Eskişehir':1472, 'Gaziantep':1582, 'Giresun':1435, 'Gümüşhane':1500,
           'Hakkari':1610, 'Hatay':1536, 'Iğdır':1487, 'Isparta':1612, 'İstanbul':1612, 'İzmir':1496, 'Kahramanmaraş':1610, ' Karabük':1369, 'Karaman':1660, 'Kars':1472,
           'Kastamonu':1364, 'Kayseri':1588, 'Kırıkkale':1460, 'Kırklareli':1460, 'Kırşehir':1509, 'Kilis':1575, 'Kocaeli':1329, 'Konya':1608, 'Kütahya':1490, 'Malatya':1599,
           'Manisa':1486, 'Mardin':1588, 'Mersin':1614, 'Muğla':1587, 'Muş':1591, 'Nevşehir':1537, 'Niğde':1620, 'Ordu':1303, 'Osmaniye':1555, ' Rize':1403, 'Sakarya':1342,
           'Samsun':1335, 'Siirt':1591, 'Sinop':1328, 'Sivas':1538, 'Şanlı Urfa':1586, 'Şırnak':1601, 'Tekirdağ':1337, 'Tokat':1431, 'Trabzon':1394, 'Tunceli':1579, 'Uşak':1540,
           'Van':1652, 'Yalova':1342, 'Yozgat':1494, 'Zonguldak ':1313}
#annual sunny hours in turkey cities
new_dicta2={'Adana':2593, 'Adıyaman': 2961, 'Afyonkarahisar':2705, 'Ağrı':2778, 'Aksaray':2886, 'Amasya':2427, 'Ankara':2611,  'Antalya':3011, ' Ardahan':2310, 'Artvin':2124,
            'Aydın':3011, 'Balıkesir':2686, 'Bartın':2376,  'Batman':2878, 'Bayburt':2398, 'Bilecik':2424, 'Bingöl':2719, 'Bitlis':2690, 'Bolu':2402, 'Burdur':2944, 'Bursa':2515,
            'Çanakkale':2807, 'Çankırı':2514, 'Çorum':2511, 'Denizli':2931, 'Diyarbakır':2613, 'Düzce':2362, 'Edirne':2697, 'Elazığ':2829, 'Erzincan':2595, 'Erzurum':2504,
             'Eskişehir':2479, 'Gaziantep':2978, 'Giresun':2285, 'Gümüşhane':2349, 'Hakkari':3508, 'Hatay':2997, 'Iğdır':3340, 'Isparta':2858, 'İstanbul':2446, 'İzmir':2986,
            'Kahramanmaraş':2913, 'Karabük':2402, 'Karaman':3007, 'Kars':2537, 'Kastamonu':2394, 'Kayseri':2842, 'Kırıkkale':2648, 'Kırklareli':2628, 'Kırşehir':2769, 'Kilis':2975,
            'Kocaeli':2373, 'Konya':2898, 'Kütahya':2559, 'Malatya':2873, 'Manisa':2840, 'Mardin':3033, 'Mersin':3015, 'Muğla':3040, 'Muş':2686, 'Nevşehir':2834, 'Niğde':2930,
            'Ordu':2263, 'Osmaniye':2954, 'Rize':2124, 'Sakarya':2358, 'Samsun':2314, 'Siirt':2828, 'Sinop':2347, 'Sivas':2653, 'Şanlı Urfa':3033, 'Şırnak':2975, 'Tekirdağ':2606,
            'Tokat':2464, 'Trabzon':2132, 'Tunceli':2716, 'Uşak':2789, 'Van':3070, 'Yalova':2424, 'Yozgat':2683, 'Zonguldak ':2380}
def city_energy():
    L=ent7.get()
    r=new_dicta.get(L)
    blank10.insert(0, r)
    
    
def gün_ışığı():
    L=ent7.get()
    r=new_dicta2.get(L)
    blank11.insert(0, r)

lbel2=Label(text="City name:" , width=14, font="Times 15  bold italic" , bg="dark turquoise")
lbel2.grid(row=0, column=4)
ent7=Entry(width=10)
ent7.grid(row=0, column=5)
btn11=Button(text="(Kwh/m2-day): ", width=14, font="Times 15  bold italic" , bg="dark turquoise", command=city_energy)
btn11.grid(row=1, column=4, padx=4, pady=4         )
blank10=Entry(width=10)
blank10.grid(row=1, column=5)
btn12=Button(text="sun bathing(h): ", width=14, font="Times 15  bold italic" , bg="dark turquoise", command=gün_ışığı)
btn12.grid(row=2, column=4)
blank11=Entry(width=10)
blank11.grid(row=2, column=5)


lbel3=Label(text="Panel area:", width=14, font="Times 15  bold italic" , bg="dark turquoise" )
lbel3.grid(row=3, column=4,)
ent8=Entry(width=10)
ent8.grid(row=3, column=5)
lbel4=Label(text="Efficient: ", width=14, font="Times 15  bold italic" , bg="dark turquoise")

lbel4.grid(row=4, column=4)
ent9=Entry(width=10)
ent9.grid(row=4, column=5)
def kazanç():#enerji kazancı
    n=int(blank10.get())
    m=int(blank11.get())
    k=int(ent8.get())
    l=int(ent9.get())
    K=int(((l/100)*k*m*n)/24)
    M=int((K/1000)*0.44)
    blank12.insert(0, K)
    blank13.insert(0, M)
btn13=Button(text="Kwh: ", width=14, font="Times 15  bold italic" , bg="dark turquoise", command=kazanç)
btn13.grid(row=5, column=4)
blank12=Entry(width=10)
blank12.grid(row=5, column=5)
lbel5=Label(text="payback(yr): ", width=14, font="Times 15  bold italic" , bg="dark turquoise")
lbel5.grid(row=6, column=4)
blank13=Entry(width=10)
blank13.grid(row=6, column=5)


def delete():
   Ent.delete(0, END)
   ent3.delete(0, END)
   blank2.delete(0, END)
   blan.delete(0, END)
   ent4.delete(0, END)
   ent41.delete(0, END)
   blank3.delete(0, END)
   blank4.delete(0, END)
   bln5.delete(0, END)
   blank5.delete(0, END)
   blank6.delete(0, END)
   blank7.delete(0, END)
   blank8.delete(0, END)
   blank14.delete(0, END)
   blank13.delete(0, END)
   blank12.delete(0, END)
   ent7.delete(0, END)
   ent8.delete(0, END)
   ent9.delete(0, END)
   blank10.delete(0, END)
   blank11.delete(0, END)
     
    
btn9=Button(text="temizle" , font="Times 15  bold italic",  bg="dark turquoise", command=delete)
btn9.grid(row=8, column=5, padx=4, pady=4)
mainloop()


