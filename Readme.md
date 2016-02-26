CentOS 6.7 + redmine 3.2 + jenkins + git + svn on docker
====

Redmie���S������̃C���[�W�ł��B

## Description

### URL

Redmine�Fhttp://<host-address>:<�w��|�[�g>/
Jenkins�Fhttp://<host-address>:<�w��|�[�g>/jenkins/
git    �Fhttp://<host-address>:<�w��|�[�g>/git/
svn    �Fhttp://<host-address>:<�w��|�[�g>/svn/

### Redmie�v���O�C���ꗗ

| �v���O�C��                     | �T�v                                                             |
|:-------------------------------|:-----------------------------------------------------------------|
| redmine_xls_export             | �`�P�b�g��Excel�ɃG�N�X�|�[�g                                    |
| redmine_plugin_views_revisions | redmine_xls_export�ɕK�v��plugin                                 |
| redmine_code_review            | ���|�W�g����diff�ɑ΂��ăR�����g��������R�[�h���r���[�v���O�C�� |
| advanced_roadmap               | ���[�h�}�b�v��\������v���O�C��                                 |
| scm-creator                    | Redmine��Ń����[�g���|�W�g�����쐬����v���O�C��                |
| redmine_drafts                 | �쐬���̃`�P�b�g��ۑ�                                           |
| clipboard_image_paste          | �`�P�b�g�ɃC���[�W���R�s�y�ł���                                 |
| redmine_banner                 | Redmine�T�C�g�㕔�ɊǗ��҂���̃��b�Z�[�W��\���ł���            |

## Demo

## Usage

docker-compose.yml�����܂����̂ŁA��������Ɏg������������܂��B

1. Redmine�̃R���e�i���쐬����f�B���N�g���ŁAhttps://github.com/jozuko/redmine-docker.git ��clone���܂��B
> git clone https://github.com/jozuko/redmine-docker.git

2. redmine-docker��docker-compose.yml���܂܂�Ă��܂��̂ŁA�����̊��ɍ��킹�ĕҏW���܂��B
> redmine:
>     image: jozuko/redmine-docker:redmine3.2
>
>     ports:
>         - "10022:22"
>         - "10180:80"
>
>     volumes:
>         - "./volumes/files/:/opt/redmine/files/"
>         - "./volumes/mysql/:/var/lib/mysql/"
>         - "./volumes/repos/:/var/opt/redmine/"
>
>     environment:
>         - REDMINE_HOST=localhost:10180
>
> # add user if you want
> #        - USER=jozuko2
> #        - USER_PASSWORD=jozuko2
> #        - ROOT_PASSWORD=rootpw
>
> # redmine smtp settngs
>         - SMTP_ENABLE=n
> #       - SMTP_METHOD=smtp
> #       - SMTP_STARTTLS=true
> #       - SMTP_HOST=smtp.gmail.com
> #       - SMTP_PORT=587
> #       - SMTP_DOMAIN=smtp.gmail.com
> #       - SMTP_AUTHENTICATION=plain
> #       - SMTP_USER=user.name@gmail.com
> #       - SMTP_PASS=gmail-password
>
> #    restart: always

image: �ύX���Ȃ��ł��������B

ports: SSH��22�|�[�g�ƁARedmine��80�|�[�g���z�X�gOS�̃|�[�g�Ɋ��蓖�Ă܂��B
       ��L�̋L�ڂ��ƁAhttp://<host-address>:10180/��redmine���N�����܂��B

volumes: redmine��mysql�̃f�[�^��ۑ�����z�X�g�̃f�B���N�g�����w�肵�܂��B
         ��L�̋L�ڂ��ƁA�ȉ��̂悤�ɂȂ�܂��B
         | �ۑ������t�@�C��               | �z�X�g�f�B���N�g���̃p�X |
         |:---------------------------------|:-----------------------------------------------------------------|
         | Redmine��attachment�t�@�C��      | <docker-compose.yml������f�B���N�g��>/volumes/files/            |
         | Redmine�̏����܂�MySQL�̃f�[�^ | <docker-compose.yml������f�B���N�g��>/volumes/mysql/            |
         | git / svn���|�W�g���f�[�^        | <docker-compose.yml������f�B���N�g��>/volumes/repos/            |


## Install

## Contribution

## Licence

[MIT](https://github.com/tcnksm/tool/blob/master/LICENCE)

## Author

[tcnksm](https://github.com/tcnksm)