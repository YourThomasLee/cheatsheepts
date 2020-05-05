- 将图片转换成base64编码(markdown使用)

```python
import base64
import argparse
if __name__=='__main__':
    parser=argparse.ArgumentParser(description='convet a image to a string...')
    parser.add_argument('-path',type=str, required=True)
    args=parser.parse_args()
    with open(args.path,'rb') as f:
        with open('output.txt','wb') as p:
            p.write(base64.b64encode(f.read()))
    print('All works was done!')
```

