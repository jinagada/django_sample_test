# 샘플 프로젝트 정보
이미 설치된 프로그램들
* conda version : 4.10.3
* Python 3.7.10 | packaged by conda-forge | (default, Feb 19 2021, 16:07:37)
* Django 3.2.9

## PyCharm 에서 장고 프로젝트 생성
### 개발서버 디렉토리 생성
* sample-test env 사용
```bash
$ mkdir /home/yelloweb/anaconda3/envs/sample-test/project/django_sample_test
```

### PyCharm에서 생성한 디릭토리와 연동하여 Django 프로젝트 생성
* PyCharm 과 연동하는 부분의 설명은 생략

### PyCharm에서 생성된 프로젝트에서 Django 개발모드 실행
* 실행결과
```bash
... 생략 ...

Django version 3.2.9, using settings 'django_sample_test.settings'
Starting development server at http://192.168.56.101:8000/
Quit the server with CONTROL-C.
```

### 개발모드에서 사용되는 8000 포트 개발서버 방화벽 설정
```bash
$ sudo firewall-cmd --permanent --add-port=8000/tcp
$ sudo firewall-cmd --reload
$ sudo systemctl restart firewalld
```

### settings.py 파일 수정
* AS-IS
```bash
... 생략 ...

ALLOWED_HOSTS = []

... 생략 ...

LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'UTC'

... 생략 ...
```

* TO-BE
```bash
... 생략 ...

ALLOWED_HOSTS = ['0.0.0.0:8000', 'localhost', '127.0.0.1', '192.168.56.101']

... 생략 ...

LANGUAGE_CODE = 'ko-kr'

TIME_ZONE = 'Asia/Seoul'

... 생략 ...
```

