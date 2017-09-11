#### css3�������� transition
##### ����c3Ч�ʼ��ߣ��任������������һ˲����ɣ��ٶȼ��졣css transition�ṩ��һ���ڸ���css����ʱ���ƶ����ٶȵķ����������������Եı任��Ϊһ������һ��ʱ��Ĺ��̡����磬��һ��Ԫ�ص���ɫ�Ӱ�ɫ��Ϊ��ɫ��ͨ������ı���������Ч�ģ�ʹ�� CSS transitions ���Ԫ�ص���ɫ���𽥴Ӱ�ɫ��Ϊ��ɫ������һ�����������ʱ仯��
**transition����**
#####  transition��һ����д���ԣ����� transition-property,transition-duration,transition-timing-function, ��transition-delay�� 
----------
##### ���������Ƿֱ�һ��transition��ÿһ������
**transition-property**
##### ָ�������ĸ����Խ�Ҫ���ж����Ĺ��� ����:
```
transition-property:width; 
transition-property:height;
transition-property:background;
```
##### ������ָ��������ԣ��м��ö��Ÿ��� ����:
```
transition-property:width,height; 
```
##### transition-property��Ĭ��ֵΪall����ʾ������ִ�ж��������Զ����ֳ����ȶ��������ǲ��ɼ̳еġ�
##### transition-property����ֵΪnone����ʾû�й��ȶ�����
----------
**transition-duration**
##### ��������Ϊ��λָ�����ȶ�������Ҫ��ʱ��,�����Բ����ܸ�ֵ�ұ���ӵ�λs/ms ����:
```
transition-duration:3s;
```
##### transition-duration����ָ�����ʱ�����ö��Ÿ�����ÿ��ʱ���ᱻӦ�õ��� transition-property ָ���Ķ�Ӧ�����ϡ����ָ����ʱ������С�����Ը�������ôʱ���б���ظ������ʱ���б��������ô���б�ᱻ�ü�����������£������б����ֲ��䡣
##### transition-property��Ĭ��ֵΪ0s����ʾ�����ֹ��ȶ��������ǲ��ɼ̳еġ�
----------
**transition-timing-function**
##### CSS�����ܵ� transition��Ӱ�죬��������ϱ仯���м�ֵ���� CSS transition-timing-function ����������������м�ֵ����������ġ�ʵ���ϣ�ͨ����������Ὠ��һ�����ٶ����ߣ����������transition�仯�����У��仯�ٶȿ��Բ��ϸı䡣

##### ���Թ涨���timing function,�ö��Ÿ�����ͨ��ʹ�� transition-property���ԣ����Ը������б�(transition property���б�)��ÿ��CSS����Ӧ����Ӧ��timing function.���timing function�ĸ��������б��������٣�ȱ�ٵ�ֵ������Ϊ��ʼֵ��ease�� �����timing function�����б�Ҫ�࣬timing function�����б�ᱻ�ض������ʵĴ�С��

##### transition-timing-function������ֵ��:

 1. ease:�ȼ��ٺ����
 2. linear:����
 3. ease-in:����
 4. ease-out������
 5. ease-in-out���ȼ��ٺ����
 6. cubic-bezier�� ����������([����������](http://cubic-bezier.com)�ڴ�վ�����ֱֵ ��ȡֵ)
 7. step-start����ͬ��steps(1,start)
              step-end����ͬ��steps(1,end)
               steps(<integer>,[,[start|end]]?)
                      ��һ������������Ϊ��������ָ�������Ĳ��� �ڶ���������ָ��ÿһ����ֵ�����仯��ʱ��㣨Ĭ��ֵend��
```
transition-timing-function: ease;
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: ease-in-out;
transition-timing-function: linear;
transition-timing-function: step-start;
transition-timing-function: step-end;

transition-timing-function: steps(4, end);
transition-timing-function: cubic-bezier(0.1, 0.7, 1.0, 0.1);
```
##### transition-timing-function��Ĭ��ֵΪease����ʾx�ȼ��ٺ���٣����ǲ��ɼ̳еġ�
----------
**transition-delay**
##### �涨�ڿ�ʼ����Ч��֮ǰ��Ҫ�ȴ���ʱ��
##### ����ָ������ӳ�ʱ�䣬ÿ���ӳٽ���ֱ�����������ָ��������ϵ�css���ԡ����ָ����ʱ������С�����Ը�������ôʱ���б���ظ������ʱ���б��������ô���б�ᱻ�ü���
##### ����ֵ����(s)�����(ms)Ϊ��λ��ȡ��ֵ��ʾ�������ں�ʱ��ʼ���ӳ�һ��ʱ������Ӧ����Ч��;��ֵ���¹���������ʼ��
```
transition-delay: 3s;
transition-delay: 2s, 4ms;
```
##### transition-delay��Ĭ��ֵΪ0s����ʾ�ȴ�0sִ�У����ǲ��ɼ̳еġ�

**������ɻᴥ�����������Ƿ����**
##### �ڱ�׼������»ᴥ��transitionend����webkit�£�����webkitTransitionEnd
ע��:������dom2����ʽ���¼�
```
var testNode = document.querySelector("#test");
		//dom0
		testNode.onmouseover=function(){
			this.style.width = "500px";
			this.style.height = "500px";
			//��transition���ǰ���� display: none���¼�ͬ�����ᱻ����
			//this.style.display="none";
			//�ӳټ�����ᴥ��
			setTimeout(function(){
					testNode.style.display="none";
			},2100)
		}
		//dom2
        testNode.addEventListener("transitionend",function(){
        	alert('���');
        });
```
#####��ÿһ��ӵ�й��ɵ�����������ɹ���ʱ���ᴥ��һ��transitionend�¼���
##### ��transition���ǰ���� display: none���¼�ͬ�����ᱻ����






 
