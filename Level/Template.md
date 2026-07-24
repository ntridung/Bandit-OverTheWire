
``` bash
ssh -p 2220 banditX@bandit.labs.overthewire.org
```
### Nếu dùng linux (Ubuntu) thì nên làm 1 cái function trong .bashrc 
``` shell
bandit () {
	ssh -p 2220 bandit$1@bandit.labs.overthewire.org
}
```
	 Nhớ dùng 'source .bashrc' để nó hoạt động 
### Template Level
``` md
# Level  -> Level 
### Mục tiêu

### Kiến thức áp dụng

## Cách giải

## Đáp án

## Password

```

