Dokcer compose practice
-----------------------

## �T�v

http://qiita.com/kohey18/items/dffe9b11d330576ab852 ���Q�l�ɂ��āA
Windows���� docker-machine �� docker-compose ���������B

## ���s���@

+ <you> �̉ӏ��͓K�X�C������B
+ ���ɁAtd-agent �� volume�̉ӏ��́AWindows �̃��[�U�[���ɐ��������킹��B
+ `docker-compose up -d` �ŋN������B 192.168.99.100 �ɃA�N�Z�X����ƁA"hello world" ���\������A
  volume �Ɏw�肵���t�H���_�ɁAflentd�o�R�Ń��O�t�@�C�����o�͂����B
+ ��~����ɂ́A `docker-compose stop`
+ ��~��A�R���e�i��j������ɂ́A `docker-compose rm`
    + �r���h�����C���[�W���폜����ɂ́A��~�ς݂ł����Ă����̃C���[�W����쐬���ꂽ�R���e�i��j������K�v������B


## ����

+ �C���[�W - docker �A�v���P�[�V���� �̐ÓI�ȃX�i�b�v�V���b�g�̂悤�Ȃ��́B`docker pull` �Ŏ擾���A`docker images` �ŕ\�������̂͂������B
+ �R���e�i - �C���[�W����쐬���ꂽ���s��(�܂��͎��s�ς�)�̃A�v���P�[�V�����̂悤�Ȃ��́B  
             �R�~�b�g����ƐV���ȃC���[�W�ɂȂ�B`docker run <�C���[�W>` �ŃR���e�i�̍쐬�Ǝ��s���s���B  
             `docker ps` �ŕ\�������̂͂������B
+ docker-machine �ɂ́A /c/Users �z�����}�E���g�����̂ŁAvolume �̘A�g���\�B
+ fulentd-address �́A dockermachin ��IP �łȂ�, localhost�ŉB
+ docker-compose �� build �� images �̂ǂ��炩�Е������w��ł���B
    + image�̏ꍇ�́A���O��build�����C���[�W���K�v�ƂȂ�B��O�҂̃C���[�W�̂悤�ȏC�����s�v�Ȃ��̂��g���ꍇ�Ȃ炱�����B
    + build �̏ꍇ�Acocker-compose.yml�̃t�H���_�� + ~.yml�̃g�b�v���x���� + �ŃC���[�W�������B
    + �Ⴆ�΁A tutorial_sinatra
    + �R���e�i���́A�����ɘA�Ԃ��t�������B�Ⴆ�΁A tutorial_sinatra_1
+ td-agent���ŏ��ɋN������K�v������A���̂��߁A sinatra�� links �� td-agent���L�q���Ă���B
    + links �̋L�q������ƁA�����N�������̃R���e�i���D�悵�ċN������邽�߁B
    + �R���e�i�̋N�����������N�ȊO�Ő���ł��Ȃ��̂��ȁB
