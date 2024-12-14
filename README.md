vector<ll> primefactors(ll n)
{
    vector<ll>res;
    for (ll i = 2; i * i <= n; i++)
    {
        if (n % i == 0)
        {
            while (n % i == 0)
            {
                n /= i;
                res.push_back(i);
            }
        }
    }
    if (n > 1)
    {
        res.push_back(n);
    }
    return res;
}


bool is_prime(ll n)
{
    if(n==1||n==0)return 0;
    else if(n==2)return 1;
    else if(n%2==0)return 0;
    for(ll i=2;i*i<=n;i++)
    {
        if(n%i==0)return 0;
    }
    return 1;
}

//vector<ll> sieve()
//{
//    vector <ll> res(1e5 + 2, 1);
//    vector <ll> vv;
//    res[0] = res[1] = 0;
//    for (ll i = 2; i <= 1e5; i++)
//    {
//        if (res[i])
//        {
//            vv.push_back(i);
//            for (ll j = i * i; j <= 1e5; j += i)
//            {
//                res[j] = 0;
//            }
//        }
//
//    }
//    return vv;
//}

//vector<bool>isPrime(N, 1); vector<int>primes;
//void linearSieve()
//{
//    isPrime[0] = isPrime[1] = 0;
//    for (ll i = 2; i < N; i++)
//    {
//        if (isPrime[i]) primes.push_back(i);
//        for (auto it : primes)
//        {
//            if (i * it >= N) break;
//            isPrime[i * it] = 0;
//            if (i % it == 0) break;
//        }
//    }
//}
//
//ll numberOfDivisors(ll n)
//{
//    int primes[] = { 2,3,5,7,11,13,17,19 };
//    ll num = 1, ans = 1;
//    for (int it : primes)
//    {
//        int c = 0;
//        while (n % it == 0)
//        {
//            n /= it;
//            c++;
//        }
//        ans *= c + 1;
//        num *= it;
//    }
//    int all = 0;
//    for (int i = 1; i < num; i++)
//    {
//        bool can = 1;
//        for (int it : primes)
//        {
//            if (i % it == 0)
//            {
//                can = 0;
//            }
//        }
//        if (can)
//        {
//            ll o = i;
//            for (; o * o < n; o += num)
//            {
//                if (n % o == 0)
//                {
//                    all += 2;
//                }
//            }
//            if (o * o == n)
//            {
//                all++;
//            }
//        }
//    }
//    return ans * all;
//}


//vector<ll> divisors(ll n)
//{
//
//
//    vector<ll>res;
//    for (ll i = 1; i * i <= n; i++)
//    {
//        if (n % i == 0)
//        {
//            res.push_back(i);
//            if (i != n / i)
//            {
//                res.push_back(n / i);
//            }
//        }
//    }
//    return res;
//}

 ll fixmod(ll a,ll b)
 {
   return (a%b+b)%b
 }

//bool is_prime(ll n)
//{
//    if (n == 1 || n == 0)return 0;
//    else if (n == 2)return 1;
//    else if (n % 2 == 0)return 0;
//    for (ll i = 2; i * i <= n; i++)
//    {
//        if (n % i == 0)return 0;
//    }
//    return 1;
//}


//ll n;
//vector<bool> isPrime;
//void sieve()
//{
//    isPrime[0] = false;
//    isPrime[1] = false;
//
//    for (ll i = 2; i * i < N; i++)
//    {
//        if (isPrime[i])
//        {
//            for (ll j = i * i; j < N; j += i)
//            {
//                isPrime[j] = false;
//            }
//        }
//    }
//}
// 
// 
//
//ll coprime(ll n)//--> number of numbers that their gcd betwen num and n ==1;
//{
//    ll ret = n;
//    for (ll i = 2; i * i <= n; i++)
//    {
//        if (n % i == 0)
//        {
//            while (n % i == 0)
//            {
//                n /= i;
//               
//            }
//            ret -= ret / i;
//        }
//    }
//    if (n > 1)
//    {
//        ret-= ret / n;
//    }
//    return ret;
//}
//
//const ll N = 1e5 + 5;
//vector<ll>co_prime(N);
//void get_co_prime()
//{
//    for (int i = 0; i < N; i++)
//    {
//        co_prime[i] = i;
//    }
//    for (ll i = 2; i < N; i++)
//    {
//        if (co_prime[i] == i)
//        {
//            for (int o = i; o < N; o += i)
//            {
//                co_prime[o] -= co_prime[o] / i;
//            }
//        }
//    }
//}


ll gcd(ll a, ll b)
{
    if (a > b) swap(a, b);
    if (a == 0)return b;
    return gcd(b % a, a);
}




int lcm(int a, int b)
{
    return a / gcd(a, b) * b;
}







//bool cmp(pair<ll, ll>& a, pair<ll, ll>& b)
//{
//    if (a.first == b.first)
//    {
//        return a.second > b.second;
//    }
//    return a.first < b.first;
//}



// NEXT PRIME *******************

//const int N = 1e5 + 1000;
//vector < bool> is_prime(N + 1, 1);
//vector<ll>next_prime(N + 1);
//void sieve()
//{
//    is_prime[0] = is_prime[1] = 0;
//    for (int i = 2; i <= N / i; i++)
//    {
//        if (is_prime[i])
//        {
//            for (int j = i * i; j <= N; j += i)
//            {
//                is_prime[j] = 0;
//            }
//        }
//    }
//    //********************************
//    // next prime
//    //********************************
//    int last = 1e9 + 7;
//    for (int i = N; i >= 0; i--)
//    {
//        next_prime[i] = last;
//        if (is_prime[i])
//        {
//            last = i;
//        }
//    }
//}
//


//  
//ll powmod(ll x, ll y)
//{
//    ll res = 1;
//    x = x % MOD;
//    if (x == 0) return 0;
//    while (y > 0)
//    {
//        if (y & 1)
//            res = (res * x) % MOD;
//        y = y >> 1;
//        x = (x * x) % MOD;
//    }
//    return res;
//}
//

// get prime factors by sieve
//ll n;
//vector<vector<int>>pf;
//void sieve()
//{
//    for (int i = 2; i < n; i++)
//    {
//        if (pf[i].empty())
//        {
//            for (int o = i; o < n; o += i)
//            {
//                pf[o].push_back(i);
//            }
//        }
//    }
//}



// get devisoros by sieve

//vector<int>d(n);
//void sieve()
//{
//    for (int i = 2; i < n; i++)
//    {
//         for(int o=i;o<n;o+=i)
//          {
//            d[o].push_back(i);
//          }
//       
//    }
//}

//ll power(ll a, ll b)
//{
//    if (b == 0)return 1;
//    ll x = power(a, b / 2);
//    x *= x;
//    if (b % 2 != 0)x *= a;
//    return x;
//}
//
//




//Kadane's Algorithm
//int n;
//cin >> n;
//ll ans = LLONG_MAX;
//ll sum = 0;
//for (int i = 0; i < n; i++)
//{
//    ll x;
//    cin >> x;
//    sum += x;
// 
//    minimum subarrat sum
//    ans = min(ans, sum);
//    sum = min(sum, 0LL);
//    
//   maxmum subarraysum
//   ans=max(ans,sum)
//   sum=max(sum,0LL)
//}
//cout << ans << e;



//**********************************
// make it Palindrome 
//     int n;
//cin >> n;
//string s;
//cin >> s;
//vector<int>arr(10, 0);
//for (char c : s)
//{
//    arr[c - '0']++;
//}
//int crt = 0;
//int in = 0;
//for (int i = 0; i < 10; i++)
//{
//    if (arr[i] % 2 != 0)
//    {
//        crt++;
//
//    }
//}
//if (crt > 1)
//{
//    cout << "NO" << e;
//}
//else
//{
//    string t = "";
//    for (int i = 0; i < 10; i++)
//    {
//        for (int j = 0; j < arr[i] / 2; j++)
//        {
//            t += to_string(i);
//        }
//    }
//    for (int i = 1; i < 10; i++)
//    {
//        if (arr[i] % 2 != 0)
//        {
//            t += to_string(i);
//        }
//    }
//
//    for (int i = 9; i >= 1; i--)
//    {
//        for (int j = 0; j < arr[i] / 2; j++)
//        {
//            t += to_string(i);
//        }
//    }
//    cout << t << e;
//
//}
//**********************************


//********************************************
//struct cmp
//{
//    string name;
//    int salary;
//
//    bool operator<(const cmp& other)const
//    {
//        return salary > other.salary;
//    }
//};
//
//struct person
//{
//    string name;
//    int arab, math, scien, engl;
//    ll total;
//    person()
//    {
//        arab = 0, math = 0, scien = 0, engl = 0;
//        total = arab + math + scien + engl;
//    }
//    bool operator <(const person& others)const
//    {
//        if (total == others.total)
//        {
//            return name < others.name;
//        }
//        return total > others.total;
//
//    }
//};
//
//bool cmp(person& a, person& b)
//{
//    if (a.total == b.total)
//    {
//        return a.name < b.name;
//    }
//    return a.total > b.total;
//}
//
//
//int main()
//{
//    ll n;
//    cin >> n;
//    vector<person>arr(n);
//    for (auto& it : arr)
//    {
//        cin >> it.s >> it.arab >> it.math >> it.scien >> it.engl;
//        it.total += it.arab + it.engl + it.math + it.scien;
//    }
//    /* cout << e;
//     cout << e;*/
//    sort(arr.begin(), arr.end(), cmp);
//    for (auto it : arr)
//    {
//        cout << it.s << " " << it.total << " " << it.arab << " " << it.math << " " << it.scien << " " << it.engl << e;
//    }
//
//    return 0;
//}
//********************************************

ll npr(ll n, ll r)
{
    if (r > n) { return 0; }
    ll p = 1;
    ll i = n - r + 1;
    while (i <= n)
    {
        p *= i++;
    }
    return p;
}

ll ncr(ll n, ll r)
{
    if (r > n)
    {
        return 0;
    }
    r = max(r, n - r); //ncr(n,r)==ncr(n,n-r);
    ll ans = 1, div = 1, i = r + 1;
    while (r <= n)
    {
        ans *= i;
        i++;
        ans /= div;
        div++;
    }
    return ans;
}


//struct coordinateCopmression 
//{
//private:
//    vector<ll>init;
//    void compress(vector<ll>& v)
//    {
//        sort(v.begin(), v.end());
//        v.erase(unique(v.begin(), v.end()), v.end());
//    }
//public:
//    coordinateCopmression(vector<ll>& v)
//    {
//        init = v;
//        compress(init);
//    }
//    int index(ll val)
//    {
//        return lower_bound(init.begin(), init.end(), val) - init.begin();
//    }
//    ll initVal(int idx)
//    {
//        return init[idx];
//    }
//};


//************************************
// if i has a matrix 
// with size k*k
// 1 1 1
// 1 0 1
// 1 1 1
// and i want to check if a matrix that has ones on its edges--> اطراف المصفوفة
// only one loop from i=0 to i<k;
// left edge --> s[i*k] --. الطرف الشمال
// right edge-->s[i*k+(k-1)]-- الطرف اليمين
// upper eged--> s[i]-- الطرف العلوب
// lowwer edge-->s[(k-1)*k+i]-- الطرف السفلي
// *************************
// inside matrik--> nasted loop start from 1 to i <k-1
// and check s[i*k+j];
// for(int i=1;i<k-1;i++)
//    {
//        for(int j=1;j<k-;j++)
//           {
//             if(s[i*k+j]==1)
//              {
//                .......
//              }
//           }
// }
//*******************************************

//*******************************************
دا كود بيطلع كل اقطار المصفوفة
  #include <iostream>
#include <vector>

using namespace std;

int main() {
    int n;
    cout << "Enter the size of the matrix (n): ";
    cin >> n;
    vector<vector<int>> matrix(n, vector<int>(n));

    // قراءة المصفوفة
    cout << "Enter the elements of the matrix:" << endl;
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            cin >> matrix[i][j];
        }
    }

    // طباعة جميع الأقطار
    for (int start = 0; start < n; ++start) {
        // القطر الذي يبدأ من الصف الأول
        cout << "Diagonal starting at (0, " << start << "): ";
        for (int i = 0, j = start; i < n && j < n; ++i, ++j) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;

        // القطر الذي يبدأ من العمود الأول (بدءًا من الصف الثاني)
        if (start > 0) { -- > لازم تتأكد انه مش اول صف لان لو اول صف كدا هتعدي علي القطر الرئيس اللي هوا الكبير مرتين
            cout << "Diagonal starting at (" << start << ", 0): ";
            for (int i = start, j = 0; i < n && j < n; ++i, ++j) {
                cout << matrix[i][j] << " ";
            }
            cout << endl;
        }
    }

    return 0;
}
//*******************************************

//*******************************************
ازاي تعرف ان فيه نقطتين ف مصوفة علي نفس العمود او نفس الصف
او نفس القطر الرئيسي 
او نفس القطر العمودي
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 100;

void solve()
{
    ll x1, y1, x2, y2;
    while (cin >> x1 >> y1 >> x2 >> y2 && x1 + x2 + y1 + y2 != 0)
    {

        if (x1 == x2 && y1 == y2)//both two postition in same position
        {
            cout << "0" << e;
        }
        else if (x1 == x2 || y1 == y2)//both two positions int same row or same column
        {
            cout << "1" << e;
        }
        else if ((x1 + y1) == (x2 + y2))//both two posistion in the second diagonal
        {
            cout << "1" << e;
        }
        else if (abs(x1 - x2) == abs(y1 - y2))// both two posisitons in the frist diagonal
        {
            cout << "1" << e;
        }
        else
        {
            cout << "2" << e;
        }
        
        



    }



//*******************************************

//************************************



//if (n & 1)
//{
//    cout << "odd" << e;
//}
//else
//{
//    cout<<"even"
//}
//
//bool knowbit(ll n, int i)
//{
//    return (n >> i) & 1;
//}
//
//ll setbit_to_one(ll n, int i)
//{
//    return n | (1 << i);
//}
//
//ll setbit_to_zero(ll& n, int i)
//{
//    return n & (~(1 << i));
//}
//
//ll flip_bit(ll n, int i)
//{
//    return n ^ (1 << i);
//}
//
//bool is_power_of_two(ll n)
//{
//    if (n == 0)
//    {
//        return 0;
//    }
//    return !(n & (n - 1));
//}


//ll nearset_power_of_two(ll n)
//{
//    // 19 --> 1 0 0 1 1
//    //        4 3 2 1 0
//    // 19 =   2^4+0+0+2^1+2^0
//    // 2^4--> nearset power of two to the number            
//    for (int i = 0; i <= 32; i--)
//    {
//        if ((n >> i) & 1)
//        {
//            return (1LL << i);
//        }
//    }
//}


//__builtin_popcount(n); --> count number of ones in binary represention  
// bitset<31>b = n; 
// b.count() --> count number of ones 
// b.set();--> convert all bits to ones
// b.reset();--> convert all bits to zeros
// b[5]=1
// cout<<b.to_ullong()<<e;-->the value after set b[5]=1
// 


//int popcount(int n)
//{
//    int crt = 0;
//    while (n)
//    {
//        crt += n & 1;
//        n >>= 1;
//    }
//    return crt;
//}
//
//

//***********************
// always
// if problem asked to increase
// and you have opetion to make operation (or) do it
// or --> alway increase the value 5|3=7
//
// if aked decreas make and operation
// x & c<= min(x,c)
//***********************


//************************
// if N is even 
// we can represent the number as sum of two primes
// 8--> 3 + 5
// 10-> 5 +5
// 6--> 3 +3
// *****************
// if N is odd we can represent the number as sum of two or three primes
// always odd number = prime + even
// 9-->3+6
// 5-->2 +3
// 15--> 5 +10 
// two if (N-2) is prime--> then N= (N-2)+2
// 9--> 2+ 7
// 15--> 2 +13
// 
// three if (N-2) is not prime then N= (n-3)+2+2
// 27-->23+2+2
// 
//************************

//********************
// if we have two number 
// a=c b = 0
// and we wnat to make a = 2*b;
// by add one sum elements
// the optimal way is to add c to two numbers
// a=c+c b= c
// then a =2c b=c;
// 
// if we have array 1,2,3,4,6
// and we want to make sum of array = 2*(xor)of array
// 
// to applay example a=c b=0;
// and add c to each number 
// 
//we want make num of them eqal value and anthor num =0
// and finally add the value of num one to ecah two numbers
// if we assum sum =x ans xor =c
// we want to make xor =0 and sum=x;
//to make xor = 0;
// make c^c;
// and add c to the sum 
// sum =x + c and xor =0
// to make sum = 2*xor
// add x+c to two num
// sum=(x+c)+(x+c) xor= x+c
// 
// ll lm=(a*b)/gcd(a,b);
// ll common divisores = n/lm;
// 
// or between all elements = or between one if theme withe product of or another elements
// x | y | z | c == x | (y | z | c)
// 
// 
//********************

//xor == sum --> في حالة لو كان الرقمين التمثيل الباينري بتاعهم مفيش بت بتساوي التانية 
او بمعني اصح الاند بينهم 0
مثال
2 5
010-->2
101-->5
^
-------
=111 -->7
اللي هوان نفسة جمع الرقمين 
يبقي قاعدة عامة الاكس اور بيساوي الجمع لو كان الاند بين الرقيمن يساوي 0

//************
// Inclusion-Exclusion
// include odd suset
// exclude even subst
//************

فيه قاعده حلوة احفظها 
a+b=(a^b)+2*(a&b)

ll count(ll l, ll r)
{
    ll s = r - l;
    return s * (s - 1) / 2;
}
ll powmod(ll x, ll y)
{
    ll res = 1;
    x = x % MOD;
    if (x == 0) return 0;
    while (y > 0)
    {
        if (y & 1)
            res = (res * x) % MOD;
        y = y >> 1;
        x = (x * x) % MOD;
    }
    return res;
}
ll add(ll a, ll b)
{
    return ((a % MOD) + (b % MOD)) % MOD;
}
ll mul(ll a, ll b)
{
    return ((a % MOD) * (b % MOD)) % MOD;
}

ll sub(ll a, ll b)
{
    return ((((a % MOD) - (b % MOD)) % MOD) + MOD) % MOD;
}

ll divide(ll a, ll b)
{
    return mul(a, powmod(b, MOD - 2));
}

ll inv(ll b)
{
    return powmod(b, MOD - 2);
}



//بتوع جون
ll power(ll n, ll p, ll MOD = 1000000007)
{
    if (!p)
        return 1;
    ll a = power(n, p / 2, MOD) % MOD;
    a *= a;
    a %= MOD;
    if (p & 1)
        return (a * (n % MOD)) % MOD;
    else
        return a;
}
 
int add(ll a, ll b) {
    return (a % mod + b % mod) % mod;
}
 
int sub(ll a, ll b) {
    return (a % mod - b % mod + mod) % mod;
}
 
int mul(ll a, ll b) {
    return (a % mod * b % mod) % mod;
}
 
int inv(ll b) {
    return power(b, mod - 2, mod);
}
 
int divid(ll a, ll b) {
    return (a % mod * inv(b) % mod) % mod;
}

vector<ll>fact(1e6);
void pre()
{
    fact[0] = 1;
    for (int i = 1; i < 1e6; i++)
    {
        fact[i] = fact[i - 1] * i % MOD;
    }
}

ll npr(ll n, ll r)
{
    return fact[n] *inv( fact[n - r])%MOD;
}

ll ncr(ll n,ll r)
{
    return fact[n] *inv(fact[n - r])%MOD *inv (fact[r])%MOD;
}


//invfact وال  fact لو عاوز تعمل بربوسيس لل 

vector<ll>fact(1e6),preinv(1e6);
void pre()
{
    fact[0] = 1;
    for (int i = 1; i < 1e6; i++)
    {
        fact[i] = fact[i - 1] * i % MOD;
    }
    for (int i = 0; i < 1e6; i++)
    {
        preinv[i] = inv(fact[i]);
    }
}

ll npr(ll n, ll r)
{
    return fact[n] *preinv[n-r]% MOD;
}

ll ncr(ll n,ll r)
{
    return fact[n] *preinv[n-r]%MOD *preinv [r]%MOD;
}

// stars and bars 
مثلا لو عندك تفحتيتن 
عاوز توزعهم علي 
 اطفال فيه كام طرييقة
 احنا ممكن نمثلها كدا ان احنا هنحط بين كل طفل والتاني حاجز 

 c | c | c
 عاوزين بقا نوزع التفاح بين الحواجز بدون تكرار
 يبقي هنعمل ncr
 ل n = fact[n-1+apples] , r=apples 
 ncr(n,r);


 // استخدم دا احسن حاجه ف التايم

 vector<ll>fact(N),preinv(N);
void pre()
{
    fact[0] = 1;
    for (int i = 1; i < N; i++)
    {
        fact[i] = fact[i - 1] * i % MOD;
    }
    preinv[N - 1] = inv(fact[N - 1]);
    for (int i = N-2; ~i; i--)
    {
        preinv[i] = preinv[i + 1] * (i + 1) % MOD;
    }
}

ll npr(ll n, ll r)
{
    return fact[n] *preinv[n-r]% MOD;
}

ll ncr(ll n,ll r)
{
    return fact[n] *preinv[n-r]%MOD *preinv [r]%MOD;
}


#include <iostream>
#include <vector>
#include <algorithm>
#include <string>
#include <set>
#include <stack>
#include <queue>
#include <deque>
#include <cmath>
#include <bitset>
#include <map>
#include <utility>
#include <iomanip>
#include <numeric>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7,N=2e5+6;


int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }
    /*pre();

     solve();*/ 

    return 0;
}


binary search double --> يعني ازاي تتعامل مع مسألةالباينري سيرش الليفيها كسور
بتعمل فور لوب يتمشي لحد 100 او ب الكتبر 150
const ll MOD = 1e9 + 7, N = 2e5 + 6;
void solve()
{
    double c, t;
    cin >> c >> t;
    double l = 0, r = 1e6, ans = 0;
    for (int i = 0; i < 100; i++)
    {
        ll mid = (l + r) / 2.0;
        if (can())
        {
            ans = mid;
            l=mid
        }
        else
        {
            r = mid;
        }
    }
    cout << fixed;
    cout << setprecision(9);
    cout << ans << e;
}

فانشكن بتجيب الجذر التكعيبي للرقم
long long cubeRoot(long long num) {
    long long l = 0, r = num, mid;
    while (l <= r) {
        mid = (l + r) / 2;
        long long cube = mid * mid * mid;

        if (cube == num)
            return mid;
        else if (cube < num)
            l = mid + 1;
        else
            r = mid - 1;
    }
    return r; 
}
دالة جاهزة 
cbrt(num);
عشان تتأكد اذا كان الرقم مكعب كامل او لا 
ll cubeRoot(ll num) 
{
    ll rt = round(cbrt(num));
    if (rt * rt * rt == num)
    {
        return rt;
    }
    return 0;
}

امثلة علي الاوردرد سيت 
xamples :
 
1 - https://w...content-available-to-author-only...j.com/problems/ORDERSET/
 
2- https://c...content-available-to-author-only...s.fi/problemset/task/1076 .. pre-request(Sliding window)
 
3- https://c...content-available-to-author-only...s.com/contest/1042/problem/D .. pre-request( prefix , subarray sum problem ( https://v...content-available-to-author-only...e.net/contest/600163#problem/B ) )
 
Another examples :
https://y...content-available-to-author-only...o.academy/topic-list/ordered_set
 
// */

 bool isPowerOfTwo(ll n)
{
    if (n <= 0)
        return false;
    return !(n & (n - 1));
}


Tavas and SaDDas 

void push_lucky(ll num)
{    //N=2e9
   
   لان لو جيت حسبت عدد الارقام المحظوظة من 1 ل9 المفروض ان الارقام كلها مكونة من ديجيت واحده  /N=2e9 طب ليه خلينا ال 
   ف بالتالي عدد الاحتمالات هتكون 2اس عدد الديجيت
   لو جيت حسبت من 10 ل 99 هتلاقي ان عدد الارقام المحظوظة 4 ليه لان عدد الاحتمالات بيساوي 2 اس عدد الديجيتس اللي هي 2 ف هتبقي ب 4
   اللي هما 44 47 74 77
   وهكذا 
   ف هوا مديك اقصي ؤقم ممكن توصلة 10 اس9 اللي هوا مليار 
   طب عدد احتمالات العدد المحظوظة للمليار االي هوا 9 ديجيت هيمون 2 اس 9
   ف عشان كدا خلينا اقصي رقم ممكن توصلة هوا 2اس9
    if (num > N)
    {
        return;
    }
    if (num)
    {
        luck.push_back(num);
    }
    push_lucky(num * 10 + 4); 
    push_lucky(num * 10 + 7);
}
void solve()
{
    ll n;
    cin >> n;
    cout << lower_bound(luck.begin(), luck.end(), n) - luck.begin() + 1 << e;

    
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    push_lucky(0);
    sort(luck.begin(), luck.end());
   /* ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }*/
    
     solve();

    return 0;
}


// مسالة bits div 1
l r بص يسطا هوا بيقولك عاوز اقل عدد يكون فيه اكبر عدد وحايد في رينج من 
ف انت عاوز تخلي البتات منورة كلها وفي نفس الوقت متعديت ال الار ومتقلش عن الالل
مثال 
لو عندك 1 3
1--> 0 0 0 1
10-->1 0 1 0

l اقل عدد عندنا هوا ال 
ف هنمشي علي كل بت فيه نحاول نخليها ب واحد
ازاي الكلاك دا 
عشان تمشي علي كل بت ف انت محتاج تعمل شيفت ليفت مع الواحد 
ايه هوا الشفت ليفت بيخليك تحرك البتاية رقم 1 شمال ف كل مرة ودا يعادل اكناك بتضرب العدد ف اتيني
مثال 
2<<=1 
2--> 0 1 0
بعد الشيفت ليفت
بقت كدا 
1 0 0
بترحك البتاية شمال حركة واحده

ف احنا دلوفتي عاوزين نمشي علي الواحد اللي هوا الليفت نخلي ابتات اللي فيه كلها تنور وفي نفس الوقت متعديش ال رايت
ف هنعمل  فور لوب بتبدأ من عند الواحد ونعمل ف كل مرة اور مع الليفت ونخزن الناتج ف  الليفت
وفيه كل مرة نخلي نعمل نخلي االوب تتوود بمقدار شيفت ليفت
مثال 
2 4
2 --> 0 1 0
4 --> 1 0 0

احنا عاوزين نخلي التاية الاولي ف الليفت منورة 
ف اول لفة ف اللوب 
i =1
l =2 
l | i <=r = 2 
l=l|r --> 010
          001
          ---
          011 -- > 3
تاني لفة عاوزين نخلي البتاية رقم 2 بواحد لو هي 0ولو هي واحد هتفضل واحد برض
ف احنا فولنا عشان تحرك البتاية اللي هواواحد دي براحتك بتعمل شيفت ليفت ف كل مرة 
تاني لفة 
i<<=1 -- > 1 <<1 =2
l=3 -- > دا اخر ناتج عملناه 
l | i <=r لان  
3 | 2 
011
010
---
011 --> لسه الشرط متكسرش وليه الناتج موصلش للرايت
ف هيدخل يعمل 
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'

#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 2e10+5;

void solve()
{
    ll l, r;
    cin >> l >> r;
    for (ll i = 1; (i | l) <= r; i <<= 1)
    {
        l |= i;
    }
    cout << l << e;
    
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    
    ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }
    
     /*solve();*/

    return 0;
}

لو عندك رفمين a ,b 
وعاوز الرقم اللي لو عملتله 
a | x == b^x
لو فيه رقم فعلا بيخلي القميتين متساويتين 
بين ال       xor  بيكون ناتج ال 
a ,b 
ف ببساطة
هتقول 
x=(a^b)
وتشوف ببقا لو عملت للقيمة دي 
x or a
and
x ^b
لو بيساوو ببقي فعلا هي دي القيمة 
لو لا يبقي مفيش قيم اصلا هتحقق التساوي دا
void solve()
{
    ll a, b;
    cin >> a >> b;
    ll res = (a ^ b);
    if ((res | a) == (res ^ b))
    {
        cout << res << e;
    }
    else
    {
        cout << "-1" << e;
    }
}



//**************************
1 + sqrt(1 + 8 * y)) / 2;
متى نستخدمها في البرمجة:
مسائل الأعداد المثلثية: عند محاولة إيجاد عدد العناصر أو المراتب في تسلسل مثلثي أو حساب توزيع الموارد أو تجميع العناصر ضمن ترتيب معين.

مسائل توزيع الكرات في صناديق: عندما تحتاج إلى حساب الحد الأقصى لعدد الصناديق أو المراتب التي يمكنك استخدامها لتوزيع عدد معين من الكرات أو العناصر.

تحليل الأداء: يمكن استخدامها لتحديد الحد الأقصى لعدد العمليات التي يمكن إجراؤها في وقت معين أو توزيع الموارد بناءً على حدود معينة.

أمثلة:
مسألة البراميد: إذا كنت تبني هرمًا من المكعبات، بحيث يحتوي الصف الأول على 1 مكعب، والصف الثاني على 2 مكعب، وهكذا، وتريد معرفة عدد الصفوف الممكنة إذا كان لديك y مكعبات، يمكنك استخدام هذه المعادلة.

التوزيع في حلقات: إذا كنت توزع عددًا معينًا من الكرات في صناديق بشكل مثلثي (أي الصندوق الأول يحتوي على كرة واحدة، الصندوق الثاني على كرتين، وهكذا)، وتريد معرفة عدد الصناديق التي يمكنك استخدامها مع y من الكرات.
//***********************


//*****************************
ف  البت ماسك 
لو عاوز تجيب اكبر اكس اور ف رينج معين 
مثلا لو مديك رقمين رايت وليفت التمثيل بتاعهم كدا
1 0 0 0 1 1 0 0
1 0 0 1 0 0 1 1
اول لما تلاقي بت محتلفة عن بت 
واكيد هتلاقي ان الاختلاف هيكون الرايت هوا اللي بواحد والليفت بزيؤوا 
لان طبعا الرايت اكبر من الليفت 
ف ساعتها اعرف ان الرقم 
انك تقدر تقلب كل البتات اللي بعد البتاية المختلفة لواحد او اصفار وهتكون جوا الرينج بين الريات والليفت
ف المثال الللي  فوق
1 0 0 0 1 1 0 0
1 0 0 1 0 0 1 1
      |
      a=0   1 1 1 1
      b=1   0 0 0 0 
      او حاجه نزلنا البتتين المتختلفين زي ما هما
      بعد كدا هتلاقي ان بعد البتات المختلفة
      تقدر تخلي قببلها كلها وحايد واكيد هتكون اكبر من الليفت وفي نفس الوقت اقل من الرايت
      ب ايدك هتلاقيهم محصورين بين اللبفن والرايت a and bولو حسبت ال 
      طب ليه عملنا الرقم التاني اللي هوا اكبر من الليفت واقل من الريات كله اصفار
      لان اول بت فيه كدا كدا بواجد واول بت ف الليفت بزيرو ف كدا كدا هتكون اكبر من الليفت واقل من الريات لان انت خليت كل اللي قبلة ب اصفارط
      ف ب التالي اكبر اكس اور
      a= 0 1 1 1 1 
      b= 1 0 0 0 0
      --------------
      a^b=1 1 1 1 1 1
      ف هتلافقي انك لو حسبت دوا هيطلعوا بساوو 2 اس رقم+1 البت -1
      مثلا عندك 8 16
      8 --> 0 1 0 0 0
      16--> 1 0 0 0 0
            |
           a=0   1 1 1 1
           b=1   0 0 0 0
           --------------
             1 1 1 1 1 == 31 
             
             الحل
             
void solve()
{
    ll l, r;
    cin >> l >> r;
    if (r-l<=1)
    {
        cout << (r^l) << e;
        return;
    }

    for (int i = 64; i >= 0; i--)
    {
        if (knowbit(r,i)!=knowbit(l,i))
        {
            cout << (1LL << i+1) - 1 << e;
            return;
        }
    }
}
//*****************************

sum of three values in array 

void solve()
{
    
    ll n, x;
    cin >> n >> x;
    vector<ll>arr(n);
    vector<pair<ll, ll>>v(n);
    for (ll i=0;i<n;i++)
    {
        cin >> arr[i];
        v[i].first = arr[i];
        v[i].second = i + 1;
    }
    sort(v.begin(), v.end());

    for (ll i = 0; i < n; i++)
    {
        ll tar = x - v[i].first;
        ll l = i+1, r = n - 1;
        while (l < r)
        {
            ll sum = v[l].first + v[r].second;
            if (sum == tar)
            {
                cout << i + 1 << " " << v[l].second << " " << v[r].second << e;
                return;
            }
            else if (tar > sum)
            {
                l++;
            }
            else
            {
                r--;
            }
        }

    }
    cout << "-1" << e;
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    
    /*ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }*/

    solve();

    return 0;
}

//**********
    // k -(k/n)--> n بيجبلك اندكس الرقم ف مجموعة ارقام اللي مش بتبقل القسمة علي 
    // مثلا لو الرقم 10 عاوز تجيب الاندكس بتاعة ف الارقام اللي مش بتقبل  القمية علي التلاتة
    // 10-(10/3)==7;
    //**********

لو عندك رقمين مثلا 3 4 وعاوز تعرف ايه الرقم اللي المفروض تضيفة علي الارفع عشان يقبل القمية علي ال3
k-(n%k)
3-(4%3)==2
4+2=6;



حل مسألة Towers cses
الفكرة هنا انك بتشوف ف كل مرة هل فيه مكعب اكبر من المكعب اللي داخل لو فيه مكعب اكبر من المكعب اللي داخل هلي غير قيمة المكعب الكبير خليها بتسازي قي مة المكعب الصغير عشان لو دخل حاجه اصغر منه تقدر تقارنها ببيه ولو دخل حاجه اكبر يبقي هتبدأ مكعب جديد
5
3 8 2 1 5

الفيكتور ف البداية فاضي 
 0 0 0 0 0 
 ف لو جيت تشوف قيمة اكبر من اول مكعب داخل مش هتلاقي 
 ف ب التالي هتبدأ مكعب جديد 
 وهتحطه ف الفيكتور 
 v ={3};
 بعد كدا ال 
 8 
 هل فيه قيمة ف الفيكتور اكبر منها 
 لا 
 يبقي هتبدأ مكعب جديد وتضيفها ف الفيكتور 
 v={3,8};
 بعد كدا ال
 2 
 هل فيه حاجه اكبر منها 
 اه ال 
 3 اكبر 
 غير بقا قيمة ال 3 خليها 2
 v={2,8};
 عن طريق انك بتخلي قيمة البوينتر اللي مشاور ع التلاتة ياوي 2
 ليه لان مثلا لو عندك مثال تاني 
 8 3 6
 او حاجه هتضيف التمانيىة
 v={8};
 بعد كدا
 ال 3 
 الخمسة اكبر من التلاتة يعني المفروض هتحطها فوق التمانية ف نفس المكعب 
 يعني المفروض تغير قيمة التمانيىة لتلاتة طب لو مغيرتش ايه اللي هيحصل 
 هتيجي عند ال 6 
 هل فيه حاجه اكبر من الستة اه فيه ال 8
 يبقي هتحطها فوق التمانية والتلاتة ومش هتبدأ برج جديد
 ودا مينفعش لازم البرج يمشي من الكبير للصغير من تحت لفوق
 ف عشان كدا لو لقينا قيمة اكبر من اللي داخله بنغير القيمة الكبير ىرللقيمة الاصغر منها

 نبدأ نكمل 
v={2,8};
بعد كدا الواحد فيه حاجه اكبر منه اه 
الاتنين
هخلاص غير قيمة الاتنين لواحد
v={1,8};
بعد كدا الخمسة فيه حاجه اكبر منه اه التمانية
v={1,5};
يبقي كدا عدد الابراج 
2
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'

#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 1e5 + 5;

void solve()
{
    ll n;
    cin >> n;
    vector<ll>v;
    for (int i = 0; i < n; i++)
    {
        ll x;
        cin >> x;
        auto it = upper_bound(v.begin(), v.end(), x);
        if (it == v.end())
        {
            v.push_back(x);
        }
        else
        {
            *it = x;
        }
    }
    cout << v.size() << e;

}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);

    /*ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }*/

    solve();

    return 0;
}

Subarray Sums I
void solve()
{
    ll n, x;
    cin >> n >> x;
    vector<ll>arr(n);
    for (auto &it : arr)
    {
        cin >> it;
    }

    map<ll, ll>mp;
    mp[0] = 1;-->عشان لو جينا طرحنا المجموع من الاكس  وطلع الناتج صفر معني كدا ان مجموع السب اراي دي بيساوي الاكس
    زي اول سب اراي ف المثال دا
    5 7
    2 4 1 2 7
    pre=2+4+1=7
    7-7=0;
    ف لو جيت تدور ف الماب عن صفر مش هتلاقية ف لازم تعلم ف البدابة ان الصفر موجود


  ll res = 0;
    ll pre = 0;
    for (ll i = 0; i < n; i++)
    {
        pre += arr[i];
        res += mp[pre - x];
        mp[pre]++;
    }
    cout << res << e;
    طب ليه عملنا الالجوريزم دا 
    بص يمعلم 
    ف المثال دا 
    5 7
    2 4 1 2 7
    او حاجه
    pre=2;
    هل 2-7 
    موجده ف الماب لا
    طب انت ليه بتدور هي موجده ف الماب ولا لا
    هقولك بعيدن نكمل
    تاني لفية
    pre=2+4
    هل موجود 6-7 ف الماب لا
    يبقي هضيف صفر للريزلت
    ويعلم ان المجموع دا موجود
    تالت لفة
    pre=2+4+1
    هل 7-7 موجود ف الماب اه موجود لان احنا علمنا ف البداية ان الصفر موجود
    ف هيروح يضيف عدد ظهور الصفر ف الماب اللي هي مرة واحده
    وهيعلم ف الماب ان ال 7 موجوده اللي هوا مجموع كل العناصر دي
    تالت لفة
    pre=2+4+1+2=9
    هل 9-7 موجوده
    اه موجوده 
    هرعفك ليه بقا بندور علي الفرق هوا موجود ولا لا 
    معني ان الفرق موجود يبقي احنا مجموع العناصر اللي معانا دا متشال منه العنصر الموجود دا يبقي كدا المجموع هيياوس الاكس
    ف ب التاالي دي تعتبر سب سيكونس يتكون مجموع اكس
    طب ليه بنضيف عدد مرات ظهورها لان ممكن تاخد واحده منهم وتسب التانية وتكون سب سيكونس تانية 
    رابع لفة 
    pre=2+4+1+2+7=16;
    هل 16 - 7 = 9 موجود ف  الماب اه موجود
    يبقي كدا فيه سب سيكونس كمان 
    ليه لان انت لو شيلت كل العناصر اللي مجموعها 9 
    هتلاقي ان مجموع السب سيكونس بقا 7 
    ف بالتالي دي سب سيكونس


}


Subarray Divisibility
*********************
الفكرة هنا ان لو فيه عددين ليهم نفس ناتج المود علي رقم معين
يبقي طرح العددين دول من بعض هيديك رقم بيقبل القسمة علي الرقم المعين دا

مثلا 
12
4 16 
4%12=4
16%12=4
4 16
ليهم مفس ناتج المود
يبقي 16 -4 =12
طرحهم اداك رقم بيقبل القسمة علي الرقم
ف احنا هنمشي ب النبدأ دا
هنعمل بريفكس سم
ونجيب لكل البريفكس المود ونحزنة لو لقينا فيه بريفكسس اتكرركت يبقياكيد طرح الارقام الليلهم نفس المود هيدوك رقم بيقبل القسمة علي الرقم 
مثال
5
arr=3 1 2 7 4
pre=3 4 6 13 17
pre_mod%5=3 4 1 3 2
هتلاحظ هنا ان الرقيمن اللي ليهم نفس ناتج المود
هما التلاتة وال 13
13-3=10
وفعلا العشرة بتقبل القسمة علي الخمسة
طب احنا عاوزين نطلع كل السب ارايز اللمكنة فيه قانون بيطلع كل السب ارايز
count_subarrays=n*(n-1)/2;
n--> عدد التكرار التشابة

*********************

#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'

#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 1e5 + 5;
ll fixmod(ll a, ll b)
{
    return (a % b + b) % b;
}

void solve()
{
    ll n;
    cin >> n;
    vector<ll>arr(n);
    for (auto &it : arr)
    {
        cin >> it;
    }
    vector<ll>pre(n, 0);
    vector<ll>pre_mod(n, 0);
    pre[0] = arr[0];
    
    for (ll i = 1; i < n; i++)
    {
        pre[i] = pre[i - 1] + arr[i];
    }
    for (ll i = 0; i < n; i++)
    {
        pre_mod[i] = fixmod(pre[i], n);
    }
   

    map< ll, ll>mp;
    mp[0] = 1;
    for (auto it : pre_mod)
    {
        mp[it]++;
    }

    ll res = 0;
    for (auto it : mp)
    {
        res += (it.second * (it.second - 1)) / 2;
    }
    cout << res << e;


}
int main()
{
ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);

    /*ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }*/

    solve();

    return 0;    
}


Maximum Sum مسألة
void solve()
{
    ll n, k;
    cin >> n >> k;
    ll ans = 0;

    vector<ll>arr(n);
    for (auto &it : arr)
    {
        cin >> it;
    }

    sort(arr.begin(), arr.end());
    vector<ll>pre(n + 1, 0);

    for (int i = 0; i < n; i++)
    {
        pre[i + 1] = pre[i] + arr[i];
    }
    
    احنا بنجرب كل الاحتمالات
    يعني بنشوف هيحصل ايه لو خدنا شيلنا عنصر كبير ومشلناش ولا واحد صغير 
    طب لو مشلناش ولا واحد كبير وشيلنا اتنين صغيرين وهكذا
    i-->عدد احتمالات انك تمسح عناصر صغير 
    y=k-i -->عدد احتملات انك تسمح عناصر كبيرة

    مثال
    6
   5 1
   2 5 1 10 6
   1 2 5 6 10
   pre={1,3,8,14,24};
   اول مرة 
   i=0 ---> يعني مش هناخد ولا عنصر صغير
   k=1-0 --> يعني هنمسح عنصر كبير

   تاني لفة
   i=1--> يعني هناخد عملية نسمح فيها عناصر صغيرة
   y=k-i=1-1=0--> يعني مش هناخد ولا عنصر كبير


    for (ll i = 0; i <= k; i++)
    {
        ll y = k - i;
        ans = max(ans, pre[n - y] - pre[2 * i]);
    }
    cout << ans << e;
   



}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);

    ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }

    /* solve();*/

    return 0;
}

*********************
تعريف اللوج او دالة اللوج
يعني ايه
log2(32)--> يعني انت عاوز تعرف ال32 بتقبل القسمة علي ال 2 كام مرة لحد ما يوصل للواحد
log3(64)--> يبقي انت عاوز تعرف ا64 بتقبل القمية علي 3 كام مرة
من الاخر اللوج بيجبلم كام مرة الرقم بيقبل القسمة علي البايز

ll crt=0;
while(n>1)
{
 n/=2;
 crt++;
}
يبقي التايم بتاع الفانكشن دي عبارة عن log(n)
لانك ف كل مرة بتقسم الرقم علي 2 


#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'

#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)

const ll MOD = 1e9 + 7, N = 1e5 + 5;


n quene
ll n;
vector<vector<char>> grid;
bool valid(int r, int c)
{   // first diagonla
    for (int r2 = r - 1, c2 = c - 1; r2 >= 0 && c2 >= 0; r2--, c2--)
    {
        if (grid[r2][c2] == 'Q')
        {
            return false;
        }
    }
    // second diagonal
    for (int r2 = r - 1, c2 = c + 1; r2 >= 0 && c2 < n; r2--, c2++)
    {
        if (grid[r2][c2] == 'Q')
        {
            return false;
        }
    }
    //vertical path
    for (int r2 = r - 1; r2 >= 0; r2--)
    {
        if (grid[r2][c] == 'Q')
        {
            return false;
        }
    }
    return true;
}
void solve(int r)//-->row
{
    if (r == n)
    {
        for (auto row : grid)
        {
            for (auto cell : row)
            {
                cout << cell;
            }
            cout << e;
        }
        cout << e;
        return;
    }
    for (int c= 0; c < n; c++)//-->اوبشن n هنا عملنا لوب لان احنا منعرفش هما كام اوبشن احنا ف مسألة الفار والجبنة رصناهم تحت بع1=ض لان احنا عارفين ان هما تو اوبشن يا اما فوق ي اما تحت اما هنا هما 
        {
            if (valid(r, c))
            {
                grid[r][c] = 'Q';
                solve(r + 1);
                grid[r][c] = '.';
            }
        }

}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n;
    grid = vector<vector<char>>(n, vector<char>(n,'.'));
    solve(0);

    return 0;
}

ف الجريد اخرك السايز يكون 
1e4*1e3
لو مديك مسألة فيها جريد اول حاجه بص عليها السايز لو لقيتخ ازيد من كدا 
يبقي مستحيل الجريد دي تترسم
ليه لان اصلا الاراي اخرها 
1e7
ف انت لما تيجي تضرب 
1e4*1e3=1e7


معلومات ف ال gcd
-------------------
gcd(a,b) =gcd(a-b,b)-->ب افتراض ان البي اصغر عنصر
gcd(a,b,c,d)==(a-b,b,c-b,d-b)-->ب افتراض ان البي اصغر عنصر
من الاخر بتثبت العنص رالصغير وبعدين تطرحه من باقي الغناصر

row gcd
------
هواعنده اتنين اراي
a=1 25 121 169
b=1 2 7 23
وعاوز تجيب 
gcd(a1+b1,a1+b2,a1+b3,a1+b4)
gcd(a2+b1,a2+b2,a2+b3,a2+b4)
gcd(a2+b1,a2+b2,a2+b3,a2+b4)

لو جينا نطبق القاعدة اللي فوق هنحاول نثبت رقم معين ويكون هوا اصغر رقم
ف هنعمل سورت للاراي
وهنعتبر ان 
a[0]-->smallest number
هنطبق القاعدة
gcd(a1+b1 , a2+b1 , a3+b1)
==
gcd(a1+b1 ,a2+b1-a1-b1 , a3+b1-a1-b1 )
==
gcd(a1+b1,a2-a1,a3-a1)

انت بسهولة هتقدر تجيب الشكل دا
gcd(a2-b1,a3-a1)
عن طريق انك هتعدي ع الاراي الاولي وتبدأها من واحد 
وتخزن ف متغير ال 
gc=gcd(gc,arr[i]-arr[0]);

طب احنا كدا ناقصنا جزء معني وبكدا يبقي جبنا 
gcd(a1+b1,,a2-a1,a3-a1)
وهي الجزء الاول 
االي هوا 
a1+b1
بما ان a1 احنا مثتينة ك اصغر عنصر
يبقي ايه اللي بيتغير ال b1
ف هنمشي علي الاراي التانية
ونعمل كدا
for(int i=0;i<m;i++)
{
 cout<<gcd(gc,a[0]+a[i])<<e;
 cout
}


traffic lights مسألة 
الفكرة هنا انت عاوز تعرف في كل مرة القيمة اللي بعد الموقع الجيد واللي قبلها
اللي بيتحلك كدا هي السيت
طب اي لازمة المالتي سيت انها تخزن الاطوال ب الترتيب التصاعدي 
ولو عاوز توصل لاكبر عنصر
cout<<*mul.rbegin();
وميزه كمان انك هتسمح الطول القديم وتضيف فيها الاطوال الجديدة بسهولة فشخ
طب ليه بنسمح الاطوال القديمة لان كل لما بتضيف موقع جديد
الطريق بيتقسم من جديد والاطوال بتتغير

void solve()
{
    ll n, x;
    cin >> n >> x;
    set<ll>ligths;
    ligths.insert(0);
    ligths.insert(n);
    multiset<ll>pos;
    pos.insert(n);
    for (ll i = 0; i < x; i++)
    {
        ll p;
        cin >> p;
        عشان تعرف تجيب النيسكت او الريفكس لازم يكون معاك ايتريتور
        ف ببساطة انت عارف كدا كدا ان النيسكت هوا العنصر الاكبر من او بيساوي القيمة اللي معاك
        ف بالتالي استخدم ايتريتور ب اللور باوند هير جعلك مكان النيسكت
        و بالتالي قيمة النيسكت هتكون هي هي قيمة الايتريتور
        طب الرفيكس
        هتستخدم فانشن البريفكس
        *std::prev(it);
        هيرجعلك القيمة اللي قبلها
        auto it =ligths.lower_bound(p);
        ll next = *it;
        ll prev = *std::prev(it);

        pos.erase(pos.find(next - prev));

        pos.insert(p - prev);
        pos.insert(next - p);

        ligths.insert(p);
        cout << *pos.rbegin() << " ";


    }

}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);

    /*ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }*/

    solve();

  
    return 0;
}

//#include<bits/stdc++.h>
//using namespace std;
//typedef long long ll;
//#define e '\n'
//
//#define ON(n,k) ((n)|(1<<(k)))
//#define OFF(n,k) ((n)& ~(1<<(k)))
//#define isON(n,k) (((n)>>(k))&1)
//
//class Rect {
//private:
//    int wid, hei;
//
//public:
//    void initi(int w, int h) {
//        wid = w;
//        hei = h;
//    }
//
//    int area() 
//    {
//        return wid * hei;
//    }
//};
//
//int main() 
//{
//    Rect rect1, rect2;
//
//    rect1.initi(5, 10);
//    rect2.initi(7, 4);
//
//    cout << "area of rect1 " << rect1.area() << endl;
//    cout << "area of rect2 " << rect2.area() << endl;
//
//
//    return 0;
//}
//****************************************************

//#include<bits/stdc++.h>
//using namespace std;
//typedef long long ll;
//#define e '\n'
//
//#define ON(n,k) ((n)|(1<<(k)))
//#define OFF(n,k) ((n)& ~(1<<(k)))
//#define isON(n,k) (((n)>>(k))&1
//
//class Car 
//{
//private:
//    int year;
//    string make;
//    int speed;
//
//public:
//    Car()
//    {
//        year = 1990;
//        make = "KIA";
//        speed = 10;
//    }
//
//    Car(int y, string m) 
//    {
//        year = y;
//        make = m;
//        speed = 0;
//    }
//
//    void acc()
//    {
//        speed += 5;
//    }
//
//    void brake()
//    {
//        if (speed >= 5)
//        {
//            speed -= 5;
//        }
//    }
//
//    int get_speed() 
//    {
//        return speed;
//    }
//};
//
//int main() {
//    Car c1(2024, "Toyota");
//
//    for (int i = 0; i < 5; i++) 
//    {
//        c1.acc();
//        cout << "current speed after accelerating: " << c1.get_speed() << " km/h" << endl;
//    }
//
//    for (int i = 0; i < 5; i++) 
//    {
//        c1.brake();
//        cout << "current speed after braking: " << c1.get_speed() << " km/h" << endl;
//    }
//
//    return 0;
//}
//***********************************************************************

#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'

#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1

class student 
{
private:
    string name;
    int id;
    int degrees[3];
    int total_degrees;

public:
    student(string n, int id1, int d[3]) {
        name = n;
        id = id1;
        for (int i = 0; i < 3; i++) {
            degrees[i] = d[i];
        }
        compute_total_degrees();
    }

    void compute_total_degrees()
    {
        total_degrees = 0;
        for (int i = 0; i < 3; i++) 
        {
            total_degrees += degrees[i];
        }
    }

    void print()  
    {
        cout << "student name: " << name << endl;
        cout << "total degrees: " << total_degrees << endl;
    }
};

int main() 
{
    string name;
    int id;
    int degrees[3];

    cout << "enter student name"<<endl;
    getline(cin, name);
    cout << "enter student id" << endl;
    cin >> id;
    cout << "enter degrees"<<endl;
    for (int i = 0; i < 3; i++) 
    {
        cin >> degrees[i];
    }

    student stu(name, id, degrees);
    stu.print();

    return 0;
}
//************************************************



//****************************************************
 شوية math
 لو مديك معادلة خطين وانت عاوز تعرف هما امتي بيتامسوا وامتي بيتقاعطعو وامتي بيتلاعدوا
 اول حاجه ساوي المعادلتين ببعض
 مثلا لو عندك 
 y1=ax2+bx+c
 y2=kx

 عاوزين نعرف هل هما متاماسان ولا متقاطعين ولا متباعدين
 ساوي المعادلتين ببعض
 ax2+bx+c=kx
 ax2+bx+c-kx=0;
 ax2+x(b-k)+c=0
x2  انت طبعا اللي يهمك هنا هي ال 
عشان تجيبها بتتجاب ب القانون العام 
لو مش فاكرة ابقا شوفة عشان مش هعرف اكتبة هنا
المهم فيه حاجه ف القانون العام اسمها المميز
المميز دا اللي هوا كل اللي تحت الجذر 
اللي هوا هيكون ف حالتنا هنا
b2-4ac
المميز دا لو ليه قيمة اكبر من صفر 
معني كدا ان الاكس ليها قيمين 
معني كدا ان الخطين بينهم تقاطع
الحالة التانية
لو المميز دا طلع بصفر معني كدا انهم متمساسين

الحالة الاخيرة 
ان لو المميز دا طلع بسالب 
يعني كدا الاكس هتطلع اعداد تخيلية
لان هيكون اللي تحت الجذر سالب
ف ب التالي هيكونوا متباعدين

//****************************************************


مسألة Strongly Composite
الاسترونج كومبوست هي الارقام اللي الديفازورز بتوععها بيكون عدد النمابر ديفازورز اقل من الارقام التانية
مثلا 
12 
1 2 3 4 6 12 
البرايم هنا اقل من بقيت الارقام 
2 3 برايم
اقل من 
4 6 12
ف بالتالي دا سترونج كومبوست

strongly composite. الفكرة هنا ان احنا هنستنتج ان ال 
من خلال كتابة الارقام ع الورق هتلاقي ان الارقام الاتسرونج كومبوست
بيكون البرايم فاكتورز بتوعها متشابة مثلا 
3*3=9
2*2=4
25=5*5
دا الو استنتاج 
ان اي رقمين متشابهين ضربهم ف بعض هيديك رقم سترونج كوموسوت
اما لو رقمين مختلفين مثلا
3*5=15
2*3=6
دول مش استرونج كومبوست
تالت استنتاج 
ان لو فيه رقم ليه 3 برايم ديفازورز مختلفين مثلا 
30 = 2 * 3 *5 
42 = 2 * 3 *7
الرقمين دول سترونج كومبوست
ف بالتالي 
كل رقمين متشابهين بيكونوا كومبوست سترونج نامبر
وكل تلت ارقام متختلفين بيمونوا رقم واحد ستورنج

ف هنعمل ماب تخزن البرايم فاكتوز بتاع كل رقم ف الاراي الالصلية
وبعدين نلف ع الماب نقسم تكرارا الارقام ع اتنين
وبالتالي دا هيكون عدد الارقام المكونة من رقمين 
وبعدين ناخد باقي القسمة عشان مثلا لو عند 2 2 2 دول هيكونوا رقم وهيتبقي 2 
ف تقوم تاخد ال 2 المتبيقة تعمل بيها رقم جديد مكون من 3 ارقام مختلفة
الحل
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 1e5 + 5;


void solve()
{
    ll n;
    cin >> n;
    map<ll, ll>mp;
    vector<ll>arr(n);
    for (auto& it : arr)
    {
        cin >> it;
        for (ll i = 2; i * i <= it; i++)
        {
            if (it % i == 0)
            {
                while (it % i == 0)
                {
                    it /= i;
                    mp[i]++;
                }
            }
        }
        if (it > 1)
        {
            mp[it]++;
        }
    }
    

    ll ans = 0;
    ll r = 0;
    for (auto it : mp)
    {
        ans += it.second / 2;
        r += it.second % 2;
    }
    cout << ans + r/3 << e;
    

    
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }
    /*solve();*/



    return 0;
}


// format of backtraking

void sol(stat s)
{
    for (check)
    {
        return 0;
    }
    // do 
    // recurs
    // undo
}


vector<vector<bool>>vis(N,vector<bool>(N,0));
vector<vector<char>> grid(N, vector<char>(N));
void solve(int r,int c)
{
    if (!valid(r, c)&&grid[r][c]=='X')
    {
        return 0;
    }
    vis[r][c] = 1;// do

    if (solve(r, c - 1)) return true;// search up
    if (solve(r, c + 1)) return true;// search down
    if (solve(r-1, c )) return true;// search left
    if (solve(r+1, c )) return true;// search right

    vis[r][c] = 0; // backtrack or undo
 
    
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    /*ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }*/
    solve();



    return 0;
}

// flood fill
vector<vector<bool>>vis(N,vector<bool>(N,0));
vector<vector<char>> grid(N, vector<char>(N));
ll cnt;
void count(int r,int c)
{
    if (!valid(r, c) || grid[r][c] == 'X' || vis[r][c])
    {
        return 0;
    }
    vis[r][c] = 1;
    cnt++;
    count(r, c - 1);
    count(r, c + 1);
    count(r-1, c);
    count(r+1, c);
    // ليه محطناش الاندو لان هوا هنا مش بيجرب طرق دا هوا بيعلم كل اللي يقدؤر يوصلة ف االي زورتة مرة متزرهوش تاني لان انت كدا هتعد مرتين

    
}

infix to postfix
rules
1- لو لقيت قوس مفتوح ضيفة ف لاستاك
2- اي اوبريتور ضرب جمع طرح ضيفها ف الاستاك بدون تفكير
3- لو لقيت اي رقم او كاركتر طلعها ف الاوت بوت
4- لو لقيت قوس مقفول افضل اعمل بوب لكل اللي ف الاستاك يعني طلعة برا ف الاوت بوت لحد ما تلاقي فتحة القوسمش بنحطها ف الاوت بوت فتحة القوس اول ما نوصلها بنمسحها وهلاص
5- قبل ما تضيف اي اوبرتور اسأل نفسك الاول هل الاوبريتور دي اعلي من الابوريتور اللي ف التوب ولا لا
6- لو لقيت ا الابوريتور اللي عليها الدور اقل من او يساوي التوب هتفضل تعمل بوب للتوب يعني تطلعه ف الاوت بوت لحد ما تلاقي ان التوب بقا اقل من الابوريتور اللي عليها الجور
7- طول مافي قوس مفتوح ف التوب وقابلك اي ابورتور ضيفها عليطول يعني متسألش هل الاوبريتور دي اعلي من القوس ولا لا
8- لو لفيت ع الاسترينج كله هشتوف بقا لو فيه حاجه لسهة موحودة ف الاستاك طلعها كلها ف الاوت بوت 

int priority(char c)
{
    if (c == '-' || c == '+')
    {
        return 1;
    }
    else if (c == '*' || c == '/')
    {
        return 2;
    }
    else if (c == '^')
    {
        return 3;
    }
    else
    {
        return 0;
    }
}

string infix_to_postfix(string exp)
{
    stack<char>st;
    string out = "";

    for (char c : exp)
    {
        if (c == ' ')
        {
            continue;
        }
        if (isdigit(c) || isalpha(c))
        {
            out += c;
        }
        else if (c == '(')
        {
            st.push(c);
        }
        else if (c == ')')
        {
            while (st.top() != '(')
            {
                out += st.top();
                st.top();
            }
            st.pop();
        }
        else
        {
            while (!st.empty()&&priority(c) <= priority (st.top()))
            {
                out += st.top();
                st.pop();
            }
            st.push(c);
        }
    }
    while (!st.empty())
    {
        out += st.top();
        st.pop();
    }
    return out;
}

int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
   /* ll t;
    cin >> t;
    while(t--)
    {
        go();
    }*/
    
    
    return 0;
}

___________________________________________
بعد ما حولنا عاوزين بقا نحسب قيمة الاكسبريشن اللي طلع دا
1- هنعمل استاك فاضي ونلوب ع الاسترينج 
2- لو لقينا رقم هنضيفة ف الاستاك
3- لو لقينا عملية حسابية هنقف ونطلع اخر رقمين ضفناهم ف الاستاك
4- بنعتبر ان التوب هوا تاني اوبريند واللي قبل التوب هوا اول اوبريند
5- بنطلعهم برا ونعمل بينهم العملية الحسابية 
6- الناتج بتعاهم بنعلمة بوش ف الاستاك
7- بعد ما تفضل  ف كل مرة تعمل نفس العمليات دي هتلاقي ان الاتساك بقا فيها رقم واحد عوا دا ناتج الامسبريشن
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 2e9;

int priority(char c)
{
    if (c == '-' || c == '+')
    {
        return 1;
    }
    else if (c == '*' || c == '/')
    {
        return 2;
    }
    else if (c == '^')
    {
        return 3;
    }
    else
    {
        return 0;
    }
}

string infix_to_postfix(string exp)
{
    stack<char>st;
    string out = "";

    for (char c : exp)
    {
        if (c == ' ')
        {
            continue;
        }
        if (isdigit(c) || isalpha(c))
        {
            out += c;
        }
        else if (c == '(')
        {
            st.push(c);
        }
        else if (c == ')')
        {
            while (st.top() != '(')
            {
                out += st.top();
                st.top();
            }
            st.pop();
        }
        else
        {
            while (!st.empty()&&priority(c) <= priority (st.top()))
            {
                out += st.top();
                st.pop();
            }
            st.push(c);
        }
    }
    while (!st.empty())
    {
        out += st.top();
        st.pop();
    }
    return out;
}

float evalu(float op1, float op2, char opera)
{
    if (opera=='+')
    {
        return op1 + op2;
    }
    else if (opera == '-')
    {
        return op1 - op2;
    }
    else if (opera == '*')
    {
        return op1 * op2;
    }
    else if (opera == '/')
    {
        return op1 / op2;
    }
    else
    {
        return 0;
    }
    
}

float postfix_evaluation(string exp)
{
    stack<float>st;
    for (char c : exp)
    {
        if (isdigit(c))
        {
            st.push(c - '0');
        }
        else
        {
            float op2 = st.top();
            st.pop();
            float op1 = st.top();
            st.pop();
            
            float res = evalu(op1, op2, c);
            st.push(res);
           
        }
    }

    return st.top();//--> final result;
}

int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
   /* ll t;
    cin >> t;
    while(t--)
    {
        go();
    }*/
    
    
    return 0;
}

الكلام دا برضه بينطبق علي البرفيكس بس بتمشي علي الاسترينج ب العكس
------------------------------------



connected components and check if is a tree or not

if edges ==nodes-1 && connected components==1 && not cyclic
then it,s a tree
بس شرطين بس كافيين لاثبات انها تري 
ان الكونكنتد كومبوناتس يكون بواحد وعدد الايدجس يساوي عدد النودز ناقص واحد 
فلابتالي اكيد دي مش هتكون سايكل 
***********************
int n, m, u, v;
vector<vector<ll>>adj;
vector<bool>visited;
void dfs(int node)
{
    visited[node] = 1;
    for (int it : adj[node])
    {
        if(!visited[it])
        {
            dfs(it);
        }
        
    }

}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m >> u >> v;
    adj.resize(n);
    visited.resize(n);
    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }

    ll connetced_com = 0;
    for (int i = 0; i < n; i++)
    {
        if (!visited[i])
        {
            connetced_com++;
            dfs(i);
        }
    }
    if(connetced_com==1&&m==n-1)
    {
      cout<<"it is a tree"<<e;
    }
    return 0;
}

************************************
check if Cyclic


int n, m, u, v;
vector<vector<ll>>adj;
vector<bool>visited;
bool iscyclic(int node,int parent)
{
    visited[node] = 1;
    for (int it : adj[node])
    {
        if (visited[it] && it != parent)
        {
            return true;
        }
        else if (!visited[it])
        {
            if (iscyclic(it, node))
            {
                return true;
            }
        }
    }
    return false;
}
*************************************
check if there a cyclic in a directed graf

const int not_vistied = 0, in_progress = 1, visited = 2;
int n, m, u, v;
vector<vector<ll>>adj;
vector<int>statement;
bool directed_cyclic(int node)
{
    statement[node] = in_progress;
    for (int it : adj[node])
    {
        if (statement[it] == not_vistied)
        {
            if (directed_cyclic(it))
            {
                return true;
            }
        }
        else if (statement[it] == in_progress)
        {
            return true;
        }
    }
    statement[node] = visited;
    return false;
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m >> u >> v;
    adj.resize(n);
    statement.resize(n);
    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
    }
    for (int i = 0; i < n; i++)
    {
        if (directed_cyclic(i))
        {
            cout << "there is a cyclic" << e;
            return 0;
        }

    }
    cout << "there is not a cyclic" << e;

    
    return 0;
}
________________________________________
topological sorting
دا بنسخدكو ف حالات زي كدا
لو طلب منك ف مسألة ترتب الحاجات معتمدة ع بعض
زي مثلا
مثلا لو قالك انت عندك 6 مواد وعشان تاخد المادة رقم 1  و 2 و 3 لازم تكون واخد المادة رقم 5 وعاوزك تطبع التريب بتاع المواد اللي المفروض هتاخدهم 
بما ن المواد دي كلها معتمدى علي المادة 5 يبيق لازم تطبع خكسة الاول وهكذا
وزي برضه
مسألة بيقولك ف
تلت عصيان مرمية ع الارض 
العصاية واحد فوق العصاية تلاتة
والعصاية رقم واحد فوق العصاية رقم اتنين
والعصاية رقم 3 فوق العصاية رقم واحد

يعني شكل العيصيان كدا
1--> 3
1-->2
3-->1
ف بالمنطق لازم تشيل واحد بعدين اتنين بعدين تلاتة


int n, m, u, v;
vector<vector<ll>>adj;
vector<bool>visited;
void dfs(int node)
{
    visited[node] = 1;
    for (int it : adj[node])
    {
        if (!visited[it])
        {
            dfs(it);
        }
    }
    cout << node << " ";
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m >> u >> v;
    adj.resize(n);
    visited.resize(n);
    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
    }
    for (int i = 0; i < n; i++)
    {
        if (!visited[i])
        {
            dfs(i);
        }
    }
    return 0;
}


//  Subtree Size Calculation
vector<vector<ll>>adj(N);
vector<ll>sub(N);
void dfs(int node, int parent)
{
    sub[node] = 1;
    for (auto it : adj[node])
    {
        if (it != parent)
        {
            dfs(it, node);
            sub[node] += sub[it];
        }
    }
    
}


طباعة الcycle 
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'

#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 200;
ll n, m, u, v;
ll start, en;
vector<vector<ll>>adj;
vector<bool>vis;
bool f;
vector<ll>parents;
bool dfs(int node,int p)
{
    vis[node] = 1;
    parents[node] = p;
    for (auto it : adj[node])
    {
    
        if (!vis[it])
        {
            if (dfs(it, node))
            {
                return true;
            }
        }
        else if(vis[it]&&it!=p)
        {
            start = it;
            en = node;
            return true;
        }
    }
    return false;
    
}

int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0);
    cin >> n >> m;
    adj.assign(n+1, vector<ll>());
    vis.assign(n+1, 0);
    parents.assign(n + 1, -1);
    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    for (int i = 1; i <= n; i++)
    {
        if (!vis[i] && dfs(i, -1))
        {
            break;
        }
    }
    if (start)
    {
        vector<ll>ans;
        ans.push_back(start);
        for (int i = en; i != start; i = parents[i])
        {
            ans.push_back(i);
        }
        ans.push_back(start);
        reverse(ans.begin(), ans.end());
        cout << ans.size() << e;
        for (auto it : ans)
        {
            cout << it << " ";
        }
        cout << e;
    }
    else
    {
        cout << "IMPOSSIBLE" << e;
    }


    return 0;
}


طباعة ساكيل ف dirtected graph

const ll not_visted = 0, in_progress = 1, visted = 2;
ll n, m, u, v;
vector<vector<ll>>adj;
vector<ll>statment;
vector<ll>parents;
bool cyc;
ll s=-1, en=-1;
bool dfs(ll node)
{
    statment[node] = in_progress;
    for (auto it : adj[node])
    {
        if (statment[it]==not_visted)
        {
          parents[it] =node;
            if (dfs(it))
            {
                return true;
            }
        }
        else if (statment[it] == in_progress)
        {
            s = it;
            en = node;
            cyc = true;
            return true;
        }
    }
    statment[node] = visted;
    return false;

}

int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0);
    cin >> n >> m;
    adj.assign(n + 1, vector<ll>());
    statment.assign(n + 1, 0);
    parents.assign(n + 1, -1);
    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
    }
    for (int i = 1; i <= n; i++)
    {
        if (statment[i] == 0 && dfs(i))
        {
            break;
        }
    }
    if (s!=-1)
    {
        vector<ll>ans;
        ans.push_back(s);
        for (int i = en; i != s; i = parents[i])
        {
            ans.push_back(i);
        }
        ans.push_back(s);
        reverse(ans.begin(), ans.end());
        cout << ans.size() << e;
        for (auto it : ans)
        {
            cout << it << " ";
        }
        cout << e;
    }
    else
    {
        cout << "IMPOSSIBLE" << e;
    }
    return 0;



 calculate max depth in graph   
ll ans;
ll n, m;
vector<vector<ll>>adj;
vector<bool>vis;
void dfs(ll node,ll depth)
{
    ans = max(ans, depth);
    for (auto it : adj[node])
    {
        if(!vis[it])
        {
            dfs(it, depth+1);
        }
        
    }
    
}

int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0);
    cin >> n;
    adj.assign(n + 1, vector<ll>());
    vis.assign(n + 1, 0);
    for (int i = 1; i <=n; i++)
    {
        ll x;
        cin >> x;
        if (x != -1)
        {
            adj[x].push_back(i);
        }
    }

    for (int i = 1; i <= n; i++)
    {
        if (!vis[i])
        {
            dfs(i,0);
        }
    }
    cout << ans+1 << e;
    return 0;


    queue
    #include<bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
//const ll MOD = 1e9 + 7, N = 100;
const int N = 100;
class Queue
{

private:
    int arr[N];
    int front = -1;
    int rear = -1;
public:

    bool is_empty()
    {
        return front == -1 && rear == -1;
    }

    bool is_full()
    {
        return rear == N - 1;
    }

    void enqueue(int val)
    {
        if (is_full())
        {
            cout << "queue is full" << e;
        }
        else
        {
            if (is_empty())
            {
                front = rear = 0;
            }
            else
            {
                rear++;
            }
            arr[rear] = val;
        }

    }

    void deqeue()
    {
        if (is_empty())
        {
            cout << "queue is empty" << e;
        }
        else
        {
            if (front == rear)
            {
                front = rear = -1;
            }
            else
            {
                front++;
            }
        }
    }
    int get_front()
    {
        if (is_empty())
        {
            cout << "queue is empty" << e;
        }
        else
        {
            return arr[front];
        }
    }

    void print()
    {
        for (int i = front; i <= rear; i++)
        {
            cout << arr[i] << " ";
        }

    }
};
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0);
    Queue q;

    q.enqueue(5);
    q.enqueue(6);
    q.enqueue(7);
    q.enqueue(9);
    q.enqueue(10);
    q.print();
    cout << e;
    q.deqeue();
    q.print();

    return 0;
}


priority_queue<int,vector<int>,greater<int>>q;


Link Cut Centroids
سينترويد هي النود اللي لو شيلناها هيبقي عندنا كونتكتد كومبونتس الاسز بتاع اقل مايمكن 
او بشكل عام هيتبقي لنا مونتكتد كومبونتنت السايز بتاعه اقل من او يساوي ال النودز علي 2
اي تري ف الدنيا فيها يا اما نود واحده سنترويد او اتنين مش بتزيد عن كدا
بيكون فيه اتنين نود سينترويد ف حالة ان كل سنرويد فيهم السايز بتاعها ب عدد الندز علي اتنين
ll n;
vector<vector<ll>>adj;
vector<ll>sz,mx_subtree;
ll mn_mx = 1e9;
vector<bool>vis;
void dfs(ll node)
{
    sz[node] = 1;
    vis[node] = 1;
    ll mx = 0;
    for (auto it : adj[node])
    {
        if (!vis[it])
        {
            dfs(it);
            sz[node] += sz[it];
            mx = max(mx, sz[it]);
        }
    }
    ll outside = n - sz[node];
    mx = max(mx, outside);
    mx_subtree[node] = mx;
    mn_mx = min(mn_mx, mx);
 
 
}
 
ll parent, child;
 
void dfs2(ll node, ll p)
{
    if (adj[node].size() == 1)
    {
        parent = p;
        child = node;
        return;
    }
 
    for (auto it : adj[node])
    {
        if (it == p)
        {
            continue;
        }
        dfs2(it, node);
    }
}
 
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    ll t;
    cin >> t;
    while(t--)
    {
        cin >> n;
        adj.assign(n + 1, vector<ll>());
        vis.assign(n + 1, 0);
        sz.assign(n + 1, 0);
        mx_subtree.assign(n + 1, 0);
        for (int i = 0; i < n - 1; i++)
        {
            ll u, v;
            cin >> u >> v;
            adj[u].push_back(v);
            adj[v].push_back(u);
        }
        dfs(1);
        vector<ll>cent;
        for (int i = 1; i <= n; i++)
        {
            if (mx_subtree[i] == mn_mx)
            {
                cent.push_back(i);
            }
        }
        if (cent.size() == 1)
        {
            cout << 1 << " " << adj[1][0] << e;
            cout << 1 << " " << adj[1][0] << e;
        }
        else
        {
            dfs2(cent[0], cent[1]);
            cout << parent << " " << child << e;
            cout << child << " " << cent[1] << e;
        }
        mn_mx = 1e9;
    }
    
    return 0;
}


**********************************************
ازاي تعمل بريفكس علي عملية ال xor
نفس البريفيكس سم بس الفرق هنا انك بتعمل دائما عملية اكسوؤ مع الارقام
ولما بتحب تجيب الاكسور ف رينج معين بتعمل كدا
pre[r] ^ pre[l-1];

في معلومة كمان مهمة ف الاكسور
مثلا 
x = 1 ^ 2 ^ 3
وقالك انا عاوزك تمسح من الاكس دا الاتنين والتلاتة وتضيف عليهم 7 مثلا
عملية الاضافة او الحذف ف الاكسور بتم عن طريق الاكسور نفسها بمعني
انت دلوقتي عاوز تمسح الاتنين والتلاتة ف هتروح تعمل اكسور مع الاتنين والتلاتة
x = (1 ^ 2 ^ 3 )^(2 ^ 3 ) = 1
طبعا انت عارف ان ف الاكسور طالما فيه ارقام شبة بعض بتطير مع بعض
طب هوا قالك ضيف بقا السبعة هتعمل ايه
هتيروح برضه تعمل اكسور مع السبعة
x = 1 ^ 7 = 6
ف قاعدة عامة لو انت عاوز تضيف علي الاكس 
قيمىة y 
وعاوز تحذف قيمة z
هتعمل كدا 
x=x ^ y ^ z

طب لو قالك عندي 
x= 2
y =3
وقالك عاوز اعمل اسواب بينهم الاتنين

ف انت عاوز تشيل الاتنين من الاكس وتضيف تلاتة
وعاوز تشيل التلاتة من الواي وتضيف 2
ف هتعمل كدا
x=2 ^ 2 ^ 3 = 3
y = 3 ^ 3 ^ 2 = 2

طب ليه بقول كل دا عشان امهد للمسألة دي 
Data Structures Fan
ف المسألة دي بيقولك 
عندك اراي الاراي
وعندك استرينج عبارى عن اصفار ووحايد
المهم عندك نوعين من الكوريز
النوع الاول
هوا انه هيديك رنج معين ف الرينج دا هتسواب الاصفار لواجايد والعسك
والنوع التاني هيقولك هاتلي ناتج الاكسور بتاع الاندكسات اللي عندها اصفار او وحايد علي حسب هوا بيحدد ايه

ف هنعمل ايه ب الكلام اللي قولناه دا
مبدائيا انت هتجيب الاكسور للعناصر اللي عندها اصفار وتخزنها ف متغير لوحدها 
وهكذا مع الوحايد
وبعدين..
هوا انت مش ف كل عملية بتعمل اسواب بين الوحايد والاصفار علي رينج ممعين
تمام اوي
يبقي كدا انت عاوز تبدل ما بين القيم اللي كانت موجودة ف المايغر اللي شايل قيمة اكسور الوحايد والمتغير اللي شايل قيمة اكسور الاصفار

بس يا سيدي هي دي فكرة المسألة والكود اهو


void solve()
{
    ll n,q;
    cin >> n;
    vector<ll>arr(n+1);
    vector<ll>pre(n+1);
    for (int i = 1; i <= n; i++)
    {
        cin >> arr[i];
        pre[i] = arr[i] ^ pre[i - 1];
    }
    string s;
    cin >> s;
    ll ones = 0, zero = 0;
    for (int i = 0; i < n; i++)
    {
        if (s[i] == '0')
        {
            zero ^= arr[i+1];
        }
        else
        {
            ones ^= arr[i+1];
        }

    }
    

    /*for (auto it : pre)
    {
        cout << it << " ";
    }
    cout << e;*/

    
    cin >> q;
    while (q--)
    {
        ll ty;
        cin >> ty;
        if (ty == 1)
        {
            ll l, r;
            cin >> l >> r;

            ll range = pre[r] ^ pre[l - 1];
            ones ^= range;
            zero ^= range;

        }
        else
        {
            ll x;
            cin >> x;
            if (x)
            {
                cout << ones;
            }
            else
            {
                cout << zero;
            }
            cout <<" ";
        }
    }
            cout << e;
       

    
}
**********************************************

***************************************************
BFS ALGORITHM
-------------
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 101, inf = 0x3f3f3f3f;
ll n, m, u, v;
vector<vector<ll>>adj;
vector<ll>dis;
void bfs(ll str)
{
    fill(dis.begin(), dis.end(), inf);
    dis[str] = 0;
    queue<ll>q;
    q.push(str);

    while (!q.empty())
    {
        ll f = q.front();
        q.pop();
        for (auto it : adj[f])
        {
            if (dis[it] == inf)
            {
                q.push(it);
                dis[f] = dis[it] + 1;
            }
        }
    }

}





int main() 
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m;
    adj.assign(n + 1, vector<ll>());
    dis.assign(n + 1, inf);

    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    bfs(0);
    for (int i = 1; i <= n; i++)
    {
        cout << i << " " << dis[i] << e;
    }
    
    return 0;
}
***************************************************

***************************************************
count connecentd compontants
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 101, inf = 0x3f3f3f3f;
ll n, m, u, v;
vector<vector<ll>>adj;
vector<ll>dis;
void bfs(ll str)
{
    dis[str] = 0;
    queue<ll>q;
    q.push(str);

    while (!q.empty())
    {
        ll f = q.front();
        q.pop();
        for (auto it : adj[f])
        {
            if (dis[it] == inf)
            {
                q.push(it);
                dis[f] = dis[it] + 1;
            }
        }
    }

}





int main() 
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m;
    adj.assign(n + 1, vector<ll>());
    dis.assign(n + 1, inf);

    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    fill(dis.begin(), dis.end(), inf);
    bfs(0);
    ll crt=0;
    for(int i=1;i<=n;i++)
    {
      if(dis[i]==inf) 
      {
        crt++;
      }
    }
    return 0;
}
***************************************************

***************************************************
check cycle in bfs
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 101, inf = 0x3f3f3f3f;
ll n, m, u, v;
vector<vector<ll>>adj;
vector<ll>dis;
bool cycle;
void bfs(ll str)
{
    fill(dis.begin(), dis.end(), inf);
    dis[str] = 0;
    queue<pair<ll,ll>>q;
    q.push({ str,-1 });

    while (!q.empty())
    {
        ll f = q.front().first;
        ll p = q.front().second;
        q.pop();
        for (auto it : adj[f])
        {
            if (dis[it] == inf)
            {
                q.push({ it,f });
                dis[it] = dis[f] + 1;
            }
            if (dis[it] != inf && it != p)
            {
                cycle = true;
            }
        }
    }

}





int main() 
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m;
    adj.assign(n + 1, vector<ll>());
    dis.assign(n + 1, inf);

    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    bfs(0);
    for (int i = 1; i <= n; i++)
    {
        cout << i << " " << dis[i] << e;
    }
    
    return 0;
}
***************************************************

****************************************************
colorful problem bfs

#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 101, inf = 0x3f3f3f3f;
const ll red = 1, not_color = 0, blue = 2;
ll n, m, u, v;
vector<vector<ll>>adj;
vector<ll>colors;
bool bfs(ll str)
{
    fill(colors.begin(), colors.end(), 0);
    colors[str] = red;
    queue<ll>q;
    q.push(str);

    while (!q.empty())
    {
        int f = q.front();
        q.pop();
        for (auto it : adj[f])
        {
            if (colors[it] == not_color)
            {
                colors[v] = (colors[f] == red ? blue : red);
            }
            else if (colors[it] == colors[f])
            {
                return false;
            }
        }
    }
}
int main() 
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m;
    adj.assign(n + 1, vector<ll>());
    colors.assign(n + 1, inf);

    for (int i = 0; i < m; i++)
    {
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    bfs(0);
    
    
    return 0;
}
************************************************

shortest path
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 1e3, inf = 0x3f3f3f3f;
int dx[] = {0,0,-1,1};
int dy[] = {1,-1,0,0};
ll n, m;
vector<pair<int, int>>adj[N];
char arr[N][N];
int strx, stry, endx, endy;
string ans = "NO", path = "";
int mnpath = 0;
int vis[N][N];
struct node
{
    int x, y, cost;
    string path;
    node(int xx, int yy, int c, string p)
    {
        x = xx, y = yy, cost=c, path = p;
    }
};
bool valid(int x, int y)
{
    return (x >= 0 && y >= 0 && x < n && y < m && !vis[x][y]&& arr[x][y] != '#');
}
void bfs()
{   
    queue<node>q;
    q.push(node(strx, stry, 0, ""));
    while (!q.empty())
    {
        node p = q.front();
        q.pop();
        vis[p.x][p.y] = 1;
        if (p.x == endx && p.y == endy)
        {
            ans = "YES";
            path = p.path;
            mnpath = p.cost;
            return;
        }
        if (valid(p.x, p.y + 1))
        {
            q.push(node(p.x, p.y + 1, p.cost + 1, p.path + 'R'));
        }
        if (valid(p.x, p.y - 1))
        {
            q.push(node(p.x, p.y - 1, p.cost + 1, p.path + 'L'));
        }
        if (valid(p.x+1, p.y))
        {
            q.push(node(p.x+1, p.y, p.cost + 1, p.path + 'D'));
        }
        if (valid(p.x-1, p.y))
        {
            q.push(node(p.x-1, p.y, p.cost + 1, p.path + 'U'));
        }


    }
}


int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m;
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            cin >> arr[i][j];
            if (arr[i][j] == 'A')
            {
                strx = i, stry = j;
            }
            else if (arr[i][j] == 'B')
            {
                endx = i, endy = j;
            }
        }
    }
    bfs();
    if (ans == "YES")
    {
        cout << "YES" << e;
        cout << mnpath << e;
        cout << path << e;
    }
    else
    {
        cout << "NO" << e;
    }

    return 0;
}
********************************************
cats and mouses (Monsters ceses)

#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n,k) ((n)|(1<<(k)))
#define OFF(n,k) ((n)& ~(1<<(k)))
#define isON(n,k) (((n)>>(k))&1)
const ll MOD = 1e9 + 7, N = 1e3, inf = 0x3f3f3f3f;
int dx[] = {0,0,-1,1};
int dy[] = {1,-1,0,0};

ll n, m;
ll mr, mc;
char arr[N][N];
vector<vector<ll>> cat_dis(N, vector<ll>(N));
bool valid1(ll x, ll y)
{
    return (x >= 0 && x < n && y >= 0 && y < m && arr[x][y] != '#' && cat_dis[x][y] == inf);
}
bool bfs()
{
    fill(cat_dis.begin(), cat_dis.end(), inf);
    queue<pair<ll, ll>>q;

    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            if (arr[i][j] == 'C')
            {
                q.push({ i,j });
                cat_dis[i][j] = 0;
            }
        }
    }

    while (!q.empty())
    {
        pair<ll, ll>node = q.front();
        q.pop();
        ll nodex = node.first;
        ll nodey = node.second;
       
        for (int i = 0; i < 4; i++)
        {
            ll x = nodex + dx[i];
            ll y = nodey + dy[i];
            if (valid1(x, y))
            {   
                cat_dis[x][y] = cat_dis[nodex][nodey] + 1;
                q.push({ x,y });
            }
            
            
        }
    }
    
}
vector<vector<ll>> mouse_dis(N, vector<ll>(N));
bool valid2(ll x, ll y)
{
    return (x >= 0 && x < n && y >= 0 && y < m && arr[x][y] != '#' && mouse_dis[x][y] == inf);
}
bool bfs_mouse(int mr,int mc)
{
    fill(mouse_dis.begin(), mouse_dis.end(), inf);
    queue<pair<ll, ll>>q;

    q.push({ mr,mc });
    mouse_dis[mr][mc] = 0;
    while (!q.empty())
    {
        pair<ll, ll>node = q.front();
        q.pop();
        ll nodex = node.first;
        ll nodey = node.second;
        for (int i = 0; i < 4; i++)
        {
            ll x = nodex + dx[i];
            ll y = nodey + dy[i];
            if (valid2(x, y))
            {
                if (cat_dis [x][y]<mouse_dis[x][y])
                {
                    if (arr[x][y] == 'E')
                    {
                        return true;
                    }
                    mouse_dis[x][y] = mouse_dis[nodex][nodey] + 1;
                    q.push({ x,y });
                }
                
            }
        }

    }
    return false;
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m;
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            cin >> arr[i][j];
            if (arr[i][j] == 'M')
            {
                mr = i, mc = j;
            }
        }
    }
    return 0;


    //*******************
    shortest pass and print the pass
    #include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n, k) ((n) | (1 << (k)))
#define OFF(n, k) ((n) & ~(1 << (k)))
#define isON(n, k) (((n) >> (k)) & 1)
const ll MOD = 1e9+7, N = 1000+5, inf = 0x3f3f3f3f;
int dx[] = { 0,0,-1,1 };
int dy[] = { 1,-1,0,0 };
char di[] = { 'R','L','U','D'};
string ans = "NO", path = "";
ll short_path = 0;
struct node
{
    ll x, y,cost;
    
    node(ll xx, ll yy, ll c)
    {
        x = xx, y = yy, cost = c;
    }

};
ll n, m;
ll strx, stry, endx, endy;
vector<vector<char>>arr(N,vector<char>(N));
vector<vector<char>>ngr(N,vector<char>(N));

vector<vector<bool>>vis(N,vector<bool>(N));
bool valid(ll x, ll y)
{
    return (x >= 0 && x < n && y >= 0 && y < m && (arr[x][y]=='.'||arr[x][y]=='B')&&!vis[x][y]);
}
void bfs()
{   
    
    queue<node>q;
    q.push(node(strx,stry,0));
    while (!q.empty())
    {
        node p = q.front();
        q.pop();

        ll nodex = p.x, nodey = p.y;
        

        if (nodex == endx && nodey == endy)
        {
            ans = "YES";
            short_path = p.cost;
            
            break;
           
        }
        for (int i = 0; i < 4; i++)
        {
            ll x = nodex + dx[i];
            ll y = nodey + dy[i];
            if (valid(x, y))
            {
                vis[x][y] = 1;
                q.push(node(x, y, p.cost + 1));
                ngr[x][y] = di[i];
            }

        }
    }
    if (ans == "YES")
    {
        cout << ans << e;
        cout << short_path << e;
        ll x = endx, y = endy;
        string path = "";

        while (x != strx || y != stry)
        {
            path += ngr[x][y];
            if (ngr[x][y] == 'R')y--;
            else if (ngr[x][y] == 'L')y++;
            else if (ngr[x][y] == 'U')x++;
            else if (ngr[x][y] == 'D')x--;
        }
        reverse(path.begin(), path.end());
        cout << path << e;
    }
    else
    {
        cout << "NO" << e;
    }

}

int main() 
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    cin >> n >> m;
    /*arr.resize(n, vector<char>(m));
    vis.resize(n, vector<bool>(m));*/

    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            cin >> arr[i][j];
            if (arr[i][j] == 'A')
            {
                strx = i, stry = j;
            }
            else if (arr[i][j] == 'B')
            {
                endx = i, endy = j;
            }
        }
    }
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            ngr[i][j] = '#';
        }
    }
    bfs();
    

    return 0;
}

}


dijkstra algorithm
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n, k) ((n) | (1 << (k)))
#define OFF(n, k) ((n) & ~(1 << (k)))
#define isON(n, k) (((n) >> (k)) & 1)
const ll MOD = 1e9 + 7, N = 5, inf = 0x3f3f3f3f;
int dx[] = { 0, 0, -1, 1, -1, -1, 1, 1 };
int dy[] = { 1, -1, 0, 0, -1, 1, -1, 1 };
char di[] = { 'R', 'L', 'U', 'D' };

void solve()
{
    int n, m;
    cin >> n >> m;
    vector<vector<pair<ll,ll>>>adj(n+1);
    vector<bool>vis(n + 1, 0);
    vector<ll>dis(n + 1, inf);
    for (int i = 0; i < m; i++)
    {
        ll u, v, z;
        cin >> u >> v >> z;
        adj[u].push_back({ v,z });

    }
    priority_queue < pair<ll, ll>, vector<pair<ll, ll>>, greater<pair<ll, ll>>>q;

    q.push({ 0,1 });//first is the cost and teh second is the node;
    while (!q.empty())
    {
        ll node = q.top().second;
        ll cost = q.top().first;
        q.pop();
        if (vis[node])continue;
        vis[node] = 1;
        dis[node] = cost;
        for (auto it : adj[node])
        {
            q.push({ it.second + cost,it.first });
        }
    }

}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    /*ll t;
    cin >> t;
    while (t--)
    {
        solve();
    }*/
    solve();
    return 0;
}

تتبع المسار ف ال bfs 
void bfs(ll st)
{
    dis[st] = 0;
    queue<ll>q;
    q.push(st);
    parent[st] = -1;
    while (!q.empty())
    {
        ll x = q.front();
        q.pop();

        if (x == n)
        {
            vector<ll>path;
            ll i = n;
            while (i != -1)
            {
                path.push_back(i);
                i = parent[i];
            }
            reverse(path.begin(), path.end());
            cout << path.size() << e;
            for (auto it : path)
            {
                cout << it << " ";
            }
            return;
        }
        for (auto it : adj[x])
        {
            if (dis[it] == inf)
            {
                dis[it] = dis[x] + 1;
                q.push(it);
                parent[it] = x;
            }
        }
    }
    cout << "IMPOSSIBLE" << e;
}

dijkstra تتبع المسار ف ال 
void solve()
{
    int n, m;
    cin >> n >> m;
    vector<vector<pair<ll,ll>>>adj(n+1);
    vector<bool>vis(n + 1, 0);
    vector<ll>dis(n + 1, inf);
    vector<ll>parent(n + 1);
    for (int i = 0; i < m; i++)
    {
        ll u, v, z;
        cin >> u >> v >> z;
        adj[u].push_back({ v,z });

    }
    priority_queue<pair<ll, pair<ll, ll>>, vector<pair<ll, pair<ll, ll>>>, greater<pair<ll, pair<ll, ll>>>> q;

    q.push({ 0,{1,-1} });//first is the cost and teh second is the node and the thrid is the parent
    while (!q.empty())
    {
        ll node = q.top().second.first;
        ll par = q.top().second.second;
        ll cost = q.top().first;
        q.pop();
        if (vis[node])continue;
        vis[node] = 1;
        dis[node] = cost;
        parent[node] = par;
        for (auto it : adj[node])
        {
            q.push({ it.second + cost,{it.first,node} });
        }
    }
    if (!vis[n])
    {
        cout << "-1" << e;
    }
    else
    {
        int i = n;
        vector<ll>path;
        while (i != -1)
        {
            path.push_back(i);
            i = parent[i];
        }
        reverse(path.begin(), path.end());
        for (auto it : path)cout << it << " ";

    }

}

bellman-ford algorithm
بس الفرق ان هنا هوا عاوز اكبر مسار 
اما لو قال ال مسار مش هتضرب الدبيو ف سالب ةهتطبع ف الاخر موجب المسافة عادي
struct edge
{
    ll from, to, w;
};
void solve()
{
    ll n, m;
    cin >> n >> m;
    vector<edge>ed(m);
    vector<ll>dis(n + 1, 1e18);
    for (int i = 0; i < m; i++)
    {
        ll u, v, w;
        cin >> u >> v >> w;
        ed[i].from = u;
        ed[i].to = v;
        ed[i].w = -w;
    }
    int f = 0;
    dis[1] = 0;
    for (int i =0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            ll from = ed[j].from;
            ll to = ed[j].to;
            ll w = ed[j].w;
            if (dis[to] > dis[from] + w)
            {
                dis[to] = dis[from] + w;
                if (i == n - 1 && to==n)
                {
                    f = 1;
                }
            }
            
            
        }
    }
    if (f)cout << "inf" << e;

    else cout << -dis[n] << e;
    

    
}
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    /*int t;
    cin >> t;
    while(t--)
    {
        solve();
    }*/
    solve();
    
    return 0;
}

bellman ford
minimum shortest path between any pair of nodes
struct edge 
{
    ll from, to, w;
};
void solve()
{
    vector<edge>ed;
    
    ll n, m;
    cin >> n >> m;
    ll mn = OO;
    for (int i = 0; i < m; i++)
    {
        ll u, v,w;
        cin >> u >> v >> w;
        ed.push_back({ u,v,w });
        mn = min(mn, w);
    }

    vector<ll>dis(n + 5, 0);
    int f = 0;
    for (int i = 1; i <= n; i++)
    {
        ed.push_back({ n + 1,i,0 });
    }

    for (int i = 0; i < n + 1; i++)
    {
        for (auto &it : ed)
        {
            ll from = it.from, to = it.to, w = it.w;
            if (dis[to] > dis[from] + w)
            {
                dis[to] = dis[from] + w;
                mn = min(mn, dis[to]);
                if (i == n)
                {
                    f = 1;
                }
            }
        }
    }
    if (f)cout << "-inf" << e;
    else cout << mn << e;
__________________________________________________________    

Linked_list 
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n, k) ((n) | (1 << (k)))
#define OFF(n, k) ((n) & ~(1 << (k)))
#define isON(n, k) (((n) >> (k)) & 1)
const ll MOD = 1e9 + 7, N = 5, inf = 0x3f3f3f3f;
int dx[] = { 0, 0, -1, 1, -1, -1, 1, 1 };
int dy[] = { 1, -1, 0, 0, -1, 1, -1, 1 };

//int dx[] = { 2, 2, -2, -2, 1, 1, -1, -1 };
//int dy[] = { 1, -1, 1, -1, 2, -2, 2, -2 };
char di[] = { 'R', 'L', 'U', 'D' };
class Node
{
public:
    int data;
    Node* next;
};

class linkedlkist
{

  Node* head;
public:

 
  linkedlkist()
  {
     head = NULL;

  }

  bool is_empty()
  {
      return head == NULL;
  }

  void insert_first(int val)
  {
      Node* newnode;
      newnode->data = val;
      if (is_empty())
      {
          newnode->next = NULL;
          head = newnode;
      }
      else
      {
          newnode->next = head;
          head = newnode;
      }
  }


  void print()
  {
      Node* temp = head;
      
      while (temp->next != NULL)
      {
          cout << temp->data << " ";
          temp = temp->next;
          
      }

  }

  bool is_found(int val)
  {
      Node* temp = head;

      while (temp->next != NULL)
      {
          if (temp->data == val) return true;

          temp = temp->next;

      }
      return false;
  }

  void insertbefore(int preval, int nval)
  {
      if (is_empty())
      {
          insert_first(nval);
          return;
      }

      if (is_found(nval))
      {
          Node* newnode = new Node();
          newnode->data = nval;

          Node* tmp = head;
          while (tmp->next->data != nval)
          {
              tmp = tmp->next;
          }
          newnode->next = tmp->next;
          tmp->next = newnode;

      }
      else
      {
          cout << "item not found" << e;
      }
      
  }

  void append(int val)
  {
      if (is_empty())
      {
          insert_first(val);
          return;
      }
      Node* newnode = new Node();
      newnode->data = val;
      Node* temp = head;
      while (temp->next != NULL)
      {
          temp = temp->next;
      }
      newnode->next = NULL; 
      temp->next = newnode;
  }

  void Delete(int val)
  {
      if (is_empty())
      {
          cout << "list is empty" << e;
          return;
      }
      Node* delptr = head;
      if (head->data == val)
      {
          head = head->next;
          delete delptr;
          return;
      }
      
      Node* prev = NULL;
      delptr = head;
      while (delptr->data != val)
      {
          delptr = delptr->next;
          prev = delptr;
      }
      prev->next = delptr->next;
      delete delptr;

      

  }


};

int main() 
{
    ios_base::sync_with_stdio(0);
      cin.tie(0), cout.tie(0);
    
    return 0;
}
دي فانشكن بتعرفك اذا كان الرقم اكس دا ممكن يتكون عن طريق مجموع ارقام اس الرقم       
k
بمعني مثلا لو قولتيك هل ينفع اكون رقم 3 عن طريق مجموع ارقام عبارة 2 اس حاجه 
3-->(2^0)+(2^1)
خلي بالك ان الاس الواحد مينفعش نستخدمة تاني 
هوا مرة واحده 
set<ll>st;
bool can(ll x, ll k)
{
    ll power = 0;
    while (x)
    {
        ll r = x % k;

        if (r > 1)return 0;

        if (r == 1)
        {
            if (st.count(power))
            {
                return 0;
            }
            st.insert(power);
        }
        x /= k;
        power++;

    }
    return 1;
}


// tree
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define e '\n'
#define ON(n, k) ((n) | (1 << (k)))
#define OFF(n, k) ((n) & ~(1 << (k)))
#define isON(n, k) (((n) >> (k)) & 1)
const ll MOD = 1e9 + 7, N = 5, inf = 1e18;
int dx[] = { 0, 0, -1, 1, -1, -1, 1, 1 };
int dy[] = { 1, -1, 0, 0, -1, 1, -1, 1 };
char di[] = { 'R', 'L', 'U', 'D' };
//int dx[] = { 2, 2, -2, -2, 1, 1, -1, -1 };
//int dy[] = { 1, -1, 1, -1, 2, -2, 2, -2 };

//preorder: [root][left][right]
//inorder:  [left][root][right]
//preorder: [left][right][root]

class Bst
{
private:
    struct Node
    {
        int data;
        Node* left;
        Node* right;

    };
    Node* root;
    void preorder(Node *temp)
    {
        if (temp == NULL)return;

        cout << temp->data << " ";
        preorder(temp->left);
        preorder(temp->right);

    }
    void inorder(Node* temp)
    {
        if (temp == NULL)return;

        preorder(temp->left);
        cout << temp->data << " ";
        preorder(temp->right);
    }

    void postorder(Node* temp)
    {
        if (temp == NULL)return;

        preorder(temp->left);
        preorder(temp->right);
        cout << temp->data << " ";

    }
    Node* remove_hel(Node* root, int data)
    {
        if (root == NULL)
        {
            return NULL;
        }
        else if (data <= root->data)
        {
            root->left=remove_hel(root->left, data);
        }
        else if (data>root->data)
        {
            root->right= remove_hel(root->right, data);
        }
        else
        {
            if (root->left == NULL)
            {
                Node* temp = root->right;
                delete root;
                return temp;
            }
            else if (root->right == NULL)
            {
                Node* temp = root->left;
                delete root;
                return temp;
            }
            else
            {
                int mx=
            }
        }
    }
public:

    Bst()
    {
        root = NULL;
    }

    void add(int val)
    {
        Node *newnode = new Node();
        newnode->data = val;
        newnode->left = NULL;
        newnode->right = NULL;
        if (is_empty())
        {
            root = newnode;
            return;
        }

        Node* temp = root;
        Node* parent = NULL;
        while (temp!=NULL)
        {
            parent = temp;
            if (val <= temp->data)
            {
                temp = temp->left;
            }
            else
            {
                temp = temp->right;
            }
        }
        if (val <= parent->data) parent->left = newnode;

        else parent->right = newnode;
    }

    bool is_empty()
    {
        return root == NULL;
    }
    void pre_order()
    {
        if (!is_empty())
        {
            preorder(root);
        }
    }
    void in_order()
    {
        if (!is_empty())
        {
            inorder(root);
        }
    }
    void post_order()
    {
        if (!is_empty())
        {
            postorder(root);
        }
    }









};
int main()
{
    ios_base::sync_with_stdio(0); cin.tie(0), cout.tie(0);
    Bst st;
    st.add(5);
    st.add(6);
    st.add(9);
    st.add(4);
    st.add(3);
    st.pre_order();
    return 0;
}

dsu
struct DSU {
private:
    vector<int>par, size;
public:
    DSU(int n) {
        par.resize(n + 5);
        size.resize(n + 5, 1);
        std::iota(par.begin(), par.end(), 0);
    }
    int getRoot(int u) {
        if (u == par[u])return u;
        return par[u] = getRoot(par[u]);
    }
    bool sameSet(int u, int v) {
        return getRoot(u) == getRoot(v);
    }
    void merge(int u, int v) {
        u = getRoot(u);
        v = getRoot(v);
        if (u == v)
            return;
        par[u] = v;
        size[v] += size[u];
    }
};

mst
struct DSU {
private:
    vector<int>par, size;
public:
    DSU(int n) {
        par.resize(n + 5);
        size.resize(n + 5, 1);
        std::iota(par.begin(), par.end(), 0);
    }
    int getRoot(int u) {
        if (u == par[u])return u;
        return par[u] = getRoot(par[u]);
    }
    bool sameSet(int u, int v) {
        return getRoot(u) == getRoot(v);
    }
    void merge(int u, int v) {
        u = getRoot(u);
        v = getRoot(v);
        if (u == v)
            return;
        par[u] = v;
        size[v] += size[u];
    }
};

struct edge
{
    ll u, v, w;
    bool operator <(const edge& others)const
    {
        return w < others.w;
    }




};
int main()
{
    ios_base::sync_with_stdio(0);  cin.tie(0), cout.tie(0);
    ll n, m;
    cin >> n >> m;
    vector<edge> ed(m);
    for (int i = 0; i < m; i++)
    {
        ll u, v, w;
        cin >> u >> v >> w;
        ed[i] = { u,v,w };
    }
    sort(ed.begin(), ed.end());

    DSU d(n);
    ll ans = 0;
    for (int i = 0; i < n; i++)
    {
        if (!d.sameSet(ed[i].u, ed[i].v))
        {
            ans += ed[i].w;
            d.merge(ed[i].u, ed[i].v);
        }
    }
    cout << ans << e;
    
    
    return 0;
}
