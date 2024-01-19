#include <bits/stdc++.h>

using namespace std;
void ptbac1() {
    long long a,b,c,tuso,gcd;
    long double xapxi;
    cout<<"nhap he so a vao day:"<<endl;
    cin>>a;
    cout<<"nhap he so b vao day:"<<endl;
    cin>>b;
    cout<<"nhap he so c vao day:"<<endl;
    cin>>c;
    tuso = (c-b);
    gcd = __gcd(tuso,a);
    tuso = tuso/gcd;
    a = a/gcd;
    if (tuso <0 && a < 0) {
        tuso = abs(tuso);
        a = abs(a);
    }
    if (a == 1) {
        cout<<"x="<<tuso;
    } else {
        cout<<"x="<<tuso<<"/"<<a<<endl;
    }
    xapxi = (c-b);
    cout<<"gia tri xap xi bang:"<<fixed<<setprecision(4)<<xapxi/a;
}
void hpt() {
    long long a,b,c,d,e,f;
    long double xapxix,xapxiy;
    cout<<"nhap he so a vao day:"<<endl;
    cin>>a;
    cout<<"nhap he so b vao day:"<<endl;
    cin>>b;
    cout<<"nhap he so c vao day:"<<endl;
    cin>>c;
    cout<<"nhap he so d vao day:"<<endl;
    cin>>d;
    cout<<"nhap he so e vao day:"<<endl;
    cin>>e;
    cout<<"nhap he so f vao day:"<<endl;
    cin>>f;
    long double x,y;
    if ((f*a) - d*c == 0 && d*b - a*e == 0) {
        cout<<"VOSONGHIEM";
        return;
    }
    if (d*b - a*e == 0) {
        cout<<"VONGHIEM";
        return;
    }
    int rutgon1,rutgon2,gcd;
    rutgon1 = f*a - d*c;
    rutgon2 = d*b - a*e;
    gcd = __gcd(rutgon1,rutgon2);
    rutgon1 = -rutgon1/gcd;
    rutgon2 = rutgon2/gcd;
    y = -((f*a)-d*c)/(d*b-a*e);
    int rutgon3,rutgon4,gcd2;

    rutgon3 = f*b-e*c;
    rutgon4 = d*b-a*e;
    gcd2 = __gcd(rutgon3,rutgon4);
    rutgon3 = rutgon3/gcd2;
    rutgon4 = rutgon4/gcd2;
    if (rutgon3 <0 && rutgon4 <0) {
        rutgon3 = abs(rutgon3);
        rutgon4= abs(rutgon4);
    }
    if (rutgon1 <0 && rutgon2 <0) {
        rutgon1 = abs(rutgon1);
        rutgon2= abs(rutgon2);
    }
    cout<<"x="<<rutgon3<<"/"<<rutgon4<<endl;
    cout<<"y="<<rutgon1<<"/"<<rutgon2<<endl;
    xapxix = rutgon3;
    xapxiy = rutgon1;
    cout<<"gia tri cua x xap xi bang:"<<fixed<<setprecision(4)<<xapxix/rutgon4<<endl;
    cout<<"gia tri cua y xap xi bang:"<<fixed<<setprecision(4)<<xapxiy/rutgon2;
    return;
}
void ptbac2 () {
    long long a,b,c,delta,mauso,tuso,sq,i,mausobandau,b2,deltabandau;
    long double xapxix,xapxix2;
    cout<<"nhap he so a vao day:"<<endl;
    cin>>a;
    cout<<"nhap he so b vao day:"<<endl;
    cin>>b;
    cout<<"nhap he so c vao day:"<<endl;
    cin>>c;
    mausobandau = 2*a;
    b2 = b;
    delta = b*b-4*a*c;
    deltabandau = b2*b2-4*a*c;
    mauso = 2*a;
    if (delta > 0) {
        long long songoaican,nhantu,nhantu2,sotrongcan,kt,tuso2,mauso2;
        sq = sqrt(delta);
        if (delta== sq*sq) {
                songoaican = sqrt(delta);
                tuso = -b+songoaican;
                tuso2 = -b-songoaican;
                mauso2 = mauso;
                long long gcd2 = __gcd(mauso2,tuso2);
                long long gcd1 = __gcd(mauso,tuso);
                tuso = tuso/gcd1;
                tuso2 = tuso2/gcd2;
                mauso = mauso/gcd1;
                mauso2= mauso2/gcd2;
                cout<<"x1="<<tuso<<"/"<<mauso<<endl;
                cout<<"x2="<<tuso2<<"/"<<mauso2<<endl;
                xapxix = (-b2+sqrt(deltabandau));
                xapxix2 = (-b2-sqrt(deltabandau));
                cout<<"gia tri cua x1 xap xi bang:"<<fixed<<setprecision(4)<<xapxix/mausobandau<<endl;
                cout<<"gia tri cua x2 xap xi bang:"<<fixed<<setprecision(4)<<xapxix2/mausobandau;

        } else {
            for (i = delta; i>=1;i--) {
                int ktsocan = sqrt(i);
                if (ktsocan * ktsocan == i && delta%i == 0) {
                        kt = i;
                        break;
                }
            }
            if (delta % kt == 0) {
                songoaican = sqrt(kt);
                sotrongcan = delta/kt;
            } else {
                sotrongcan = delta % kt;
                songoaican = sqrt(kt);
            }
        nhantu = __gcd(b,songoaican);
        b = b/nhantu;
        songoaican = songoaican/nhantu;
        nhantu2 = __gcd(mauso,nhantu);
        nhantu = nhantu/nhantu2;
        mauso = mauso/nhantu2;
        b = b*nhantu;
        songoaican = songoaican*nhantu;
        if (mauso == 1) {
            int again = __gcd(b, songoaican);
        b = -b/again;
        songoaican = songoaican/again;
        }
        cout<<"x1="<<-b<<"+"<<songoaican<<"sqrt("<<sotrongcan<<")"<<"/"<<mauso<<endl;
        cout<<"x2="<<-b<<"-"<<songoaican<<"sqrt("<<sotrongcan<<")"<<"/"<<mauso<<endl;
        xapxix = (-b2+sqrt(deltabandau));
        xapxix2 = (-b2-sqrt(deltabandau));
        cout<<"gia tri cua x1 xap xi bang:"<<fixed<<setprecision(4)<<xapxix/mausobandau<<endl;
        cout<<"gia tri cua x2 xap xi bang:"<<fixed<<setprecision(4)<<xapxix2/mausobandau;
        }
    }
    if (delta == 0) {
        a = a*2;
        int gcdkt = __gcd(a,b);
        a = a/gcdkt;
        b = -b/gcdkt;
        cout<<"x1=x2="<<b<<"/"<<a;
    }
    if (delta < 0) {
        cout<<"PHUONG TRINH VO NGHIEM";
    }
}
int main()
{
    cout<<"caculator tinh he phuong trinh va phuong trinh bac 2"<<endl;
    cout<<"made by qixi :)"<<endl;
    cout<<"luu y: co the chuong trinh tinh sai ket qua mong cac ban thong cam :,) "<<endl;
    cout<<"he phuong trinh chon 1"<<endl;
    cout<<"phuong trinh bac 2 chon 2"<<endl;
    cout<<"phuong trinh bac 1 chon 3"<<endl;
    int choose,chon,d;
    d = 0;
    chon = 0;
    while (chon != 1) {
        cout<<"enter number here =>"<<endl;
        cin>>choose;
        if (choose == 1) {
        hpt();
        chon = 1;
        break;
    }
    if (choose == 2) {
        ptbac2();
        chon = 1;
        break;
    }
    if (choose == 3) {
        ptbac1();
        chon = 1;
        break;
    }
    if (choose != 2 || choose !=1 || choose !=3) {
        d++;
        if (d<10) {
            cout<<"chon lai di bruh ._.  "<<endl;
        }

        if (d >=10) {
            cout<<"dua khong vui dau chon lai di >:( "<<endl;
        }
        if (d>=15) {
            cout<<"eo tinh cho nua bye fuck you"<<endl;
            return 0;
        }
    }
    }
    return 0;
}
