

### bitset  


---  

첫 번째로 bitset을 정리합니다.  
알고리즘 stl중 변수 자체로 비트연산이 가능하다.  
  
선언방법은 다음과 같다.  
  
{% highlight cpp %}  
- bitset<8> bit;         // 0,0,0,0,0,0,0,0  
- bitset<8> bit(16)      // 0,0,0,0,1,0,0,0  
- bitset<8> bit("10101") // 0,0,0,1,0,1,1,0  
  
{% endhighlight %}  
  
bit 안에 변수를 확인하는 방법은 다음과 같다.  

{% highlight cpp %}  
bitset<8> b(18); .. // 0,0,0,1,0,0,1,0  

for(int i = 0 ; i < b.size(); i++) {
	cout << i << ": " << b[i] << '\n';
	// 참고로 작은 비트(오른쪽비트) 가 0 이다.
}

{% endhighlight %}
  
bitset의 명력어론 다음과 같다.  

{% highlight cpp %}  
bitset<10> b(88);   // 0,0,0,1,0,1,1,0,0,0  
cout << b << '\n';  // 0001011000

cout << b.test(4) <<'\n'; // 1
cout << b.test(5) <<'\n'; // 0

b.set(0); // 0번째로 1로 바꾼다.
cout << b << '\n'; // 0,0,0,1,0,1,1,0,0,1

b.reset(0); // 0번째를 0으로바꾼다.
cout << b << '\n'; // 0,0,0,1,0,1,1,0,0,0

b.flip(2); // 2번째를 ~연산 해준다.
cout << b << '\n'; // 0,0,0,1,0,1,1,1,0,1


// 또한 괄호 안에 숫자를 쓰지않으면 변수 전체에 연산을 해준다.
b.flip(); 
cout << b << '\n'; // 1,1,1,0,1,0,0,0,1,0

b.set(); 
cout << b << '\n'; // 1,1,1,1,1,1,1,1,1,1

b.reset(); 
cout << b << '\n'; // 0,0,0,0,0,0,0,0,0,0

{% endhighlight %}  
  
변수안에 비트 개수를 세거나 확인하는 연산은 다음과 같다.  
{% highlight cpp %}   
bitset<8> b(18); // 0,0,0,1,0,0,1,0

cout << b << '\n' //0001011000

cout << b.all()  << '\n' // false
cout << b.any()  << '\n' // true
cout << b.none() << '\n' // false
cout << b.count()<< '\n' // 2

{% endhighlight %}    
  
마지막으로 변수끼리 & , | , ^(xor) , ~ 연산이 가능하다.  
{% highlight cpp %}  
bitset<8> bit1(18); // 0,0,0,1,0,0,1,0
bitset<8> bit2(6);  // 0,0,0,0,0,1,1,0

cout << (bit1 & bit2) << '\n'; // 00000010
cout << (bit1 | bit2) << '\n'; // 00010110

cout << (bit1 ^ bit2) << '\n'; // 00010101

cout << (bit1 << 2)   << '\n'; // 01001000
cout << (bit2 >> 2)   << '\n'; // 00000001

cout << ~(bit1)       << '\n'; // 11101101


{% endhighlight %}   

