# OS Term Project

## Requirements
- 모든 명령어 구현
- Log Area 구현
  - 적절한 섹터 하나 또는 두 개를 Log Area로 할당
  - 섹터 위치는 임의로 선택
  - 파일시스템 연산(파일생성/삭제, 디렉토리 생성/삭제 등) 실행 전 연산에 대한 정보 기록
  - 연산마다 기록할 로그 정보 직접 설계
  - 연산 수행 후 로그 정보 삭제
  - 파일 시스템 부팅 후 로그 정보 존재시 마지막 연산 무효화 (실행가능한 경우 실행 후 로그 삭제)

## 파일 구성
| 파일명 | 설명 |
|--------|------|
| Readme.txt | 이 파일 |
| diskemul.c | 하드디스크 에뮬레이터 |
| Disk_Stat() | 하드디스크의 섹터 수를 돌려줌 |
| Disk_ReadSector(sector, buf) | 섹터에서 512바이트를 읽어옴 |
| Disk_WriteSector(sector, buf) | 섹터로 512바이트를 기록 |
| disk_driver.h | 디스크 에뮬레이터에서 사용하는 오류와 디스크 크기를 정의 fs.c에서 디스크 에뮬레이터를 사용하기 위해서는 이 헤더파일을 include해야 한다. |
| fs.c | 학생들이 작성해야 하는 파일 시스템 비어있는 루틴들을 작성해야 한다. |
| fs.h | 파일 시스템의 오류 코드들이 정의되어 있음. mini_sh.c에서 파일 시스템을 호출하기 위해서는 이 헤더파일을 include해야 한다.|
| mini_sh.c | 미니 쉘로 사용자의 명령을 해석하여 파일 시스템을 호출하여 그 결과를 화면에 보여줌. 명령어 해석기|
| Makefile | Linux나 UNIX에서 파일 시스템을 빌드하는 메이크파일 |

## 미니 쉘 실행 파일 생성 및 실행

#### Linux / UNIX 상에서 make 명령어 실행
```
$ make
$ ./minish
```

#### 프롬프트
```
msh #
```

#### 미니쉘 명령어
| 명령어 | 설명 | 사용 예 |
|------|-----|----|
| quit | 미니 쉘의 수행을 종료한다. | msh # quit |
| format | 파일 시스템을 포맷한다.<br>현재 상태는 FAT 기반으로 포맷 | msh # format |
| mount | 파일 시스템을 마운트한다. | msh # mount |
| dir | 현재 디렉토리에 존재하는 파일들을 보여준다.<br>처음에 기본으로 루트 디렉토리가 현재 디렉토리가 된다. | msh # dir |
| del | 현재 디렉토리에서 파일을 삭제한다. | msh # del filename |
| mkfile | 현재 디렉토리에 원하는 크기의 파일을 생성한다.<br>파일 내용은 임의의 문자로 채운다.<br>예시는 500 Byte testfile 생성. | msh # mkfile testfile 500 |
| type | 파일의 내용을 보여준다. | msh # type testfile |
| mkdir | 새로운 디렉토리를 만든다. | msh # mkdir child_dir |
| rmdir | 디렉토리를 삭제한다. | msh # rmdir child_dir |
| cd | 새로운 디렉토리로 이동한다. | msh # cd child_dir |
| fat | FAT를 보여줍니다. | 학생들이 작성할 것 |
| fsck | 파일 시스템 오류가 있는지를 검사. | 학생들이 작성할 것 |

#### 초기 파일 시스템 테스트
```
msh # format
msh # mount
msh # dir
```
- 초기에는 quit, format, mount, dir 명령만 작동
- 미니 쉘 구동시 반드시 format, mount 명령어 먼저 수행 후 다른 명령 입력
- 기타 명령은 fs.c 완성을 통해 사용 가능


## 프로젝트 수행 과정

#### 코드의 개요

#### 사용 알고리즘

#### 프로젝트 수행 중 겪었던 문제점

#### 문제점 해결방안
