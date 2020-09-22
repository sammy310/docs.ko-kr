---
title: Docker를 사용하여 앱 컨테이너화 자습서
description: 이 자습서에서는 Docker를 사용하여 .NET Core 애플리케이션을 컨테이너화하는 방법을 알아봅니다.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b6775c760ef3f5bf1c9519430b038f149c9cf30f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538503"
---
# <a name="tutorial-containerize-a-net-core-app"></a>자습서: .NET Core 앱 컨테이너화

이 자습서에서는 Docker를 사용하여 .NET Core 애플리케이션을 컨테이너화하는 방법을 알아봅니다. 컨테이너에는 변경할 수 없는 인프라를 제공하고, 이식 가능한 아키텍처를 제공하고, 확장성을 사용하는 등의 많은 기능과 이점이 있습니다. 이미지를 사용하여 로컬 개발 환경이나 프라이빗 클라우드 또는 퍼블릭 클라우드용 컨테이너를 생성할 수 있습니다.

이 자습서에서는 다음과 같은 작업을 수행합니다.

> [!div class="checklist"]
>
> - 간단한 .NET Core 앱 만들기 및 게시
> - .NET Core용 Dockerfile 만들기 및 구성
> - Docker 이미지 빌드
> - Docker 컨테이너 만들기 및 실행

.NET Core 애플리케이션용 Docker 컨테이너 빌드 및 배포 작업을 알아봅니다. Docker 플랫폼은 Docker 엔진을 사용하여 Docker 이미지로 앱을 신속하게 빌드하고 패키지합니다.    이 이미지는 계층화된 컨테이너에서 배포되고 실행되도록 *Dockerfile* 형식으로 작성됩니다.

> [!NOTE]
> 이 자습서는 ASP.NET Core 앱에는 적합하지 **않습니다**. ASP.NET Core를 사용하는 경우 [ASP.NET Core 애플리케이션을 컨테이너화하는 방법 알아보기](/aspnet/core/host-and-deploy/docker/building-net-docker-images) 자습서를 참조하세요.

## <a name="prerequisites"></a>사전 요구 사항

다음 필수 구성 요소를 설치합니다.

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)\
.NET Core가 설치되어 있는 경우 `dotnet --info` 명령을 사용하여 사용 중인 SDK를 확인합니다.
- [Docker Community Edition](https://www.docker.com/products/docker-desktop)
- *Dockerfile* 및 .NET Core 예제 앱의 임시 작업 폴더입니다. 이 자습서에서는 이름 *docker-working*이 작업 폴더로 사용됩니다.

## <a name="create-net-core-app"></a>.NET Core 앱 만들기

Docker 컨테이너가 실행되는 .NET Core 앱이 필요합니다. 아직 없는 경우, 터미널을 열고 작업 폴더를 만든 후 입력합니다. 작업 폴더에서 다음 명령을 실행하여 *app*이라는 하위 디렉터리에서 새 프로젝트를 만듭니다.

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

폴더 트리는 다음과 같이 나타납니다.

```
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
```

`dotnet new` 명령은 *App*이라는 새 폴더를 만들고 “Hello World” 콘솔 애플리케이션을 생성합니다. 디렉터리를 변경하고 터미널 세션에서 *App* 폴더로 이동합니다. `dotnet run` 명령을 사용하여 앱을 시작합니다. 애플리케이션이 실행되고 명령 아래에 `Hello World!`를 출력합니다.

```dotnetcli
dotnet run
Hello World!
```

기본 템플릿은 터미널에 출력한 후 종료되는 앱을 만듭니다. 이 자습서에서는 무한 반복되는 앱을 사용합니다. 텍스트 편집기에서 *Program.cs* 파일을 엽니다.

> [!TIP]
> Visual Studio Code를 사용하는 경우 이전 터미널 세션에서 다음 명령을 입력합니다.
>
> ```console
> code .
> ```
>
> 이렇게 하면 Visual Studio Code에서 프로젝트가 포함된 *App* 폴더가 열립니다.

*Program.cs*는 다음 C# 코드와 같이 표시됩니다.

```csharp
using System;

namespace NetCore.Docker
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

1초마다 숫자를 계산하는 다음 코드로 파일을 바꿉니다.

```csharp
using System;
using System.Threading.Tasks;

namespace NetCore.Docker
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                Console.WriteLine($"Counter: {++counter}");
                await Task.Delay(1000);
            }
        }
    }
}
```

파일을 저장하고 `dotnet run`을 사용하여 프로그램을 다시 테스트합니다. 이 앱은 무한 실행된다는 점을 명심하세요. 취소 명령 <kbd>CTRL+C</kbd>를 사용하여 앱을 중지합니다. 다음은 출력 예제입니다.

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

명령줄의 숫자를 앱에 전달하면 해당 양까지만 계산되고 종료됩니다. 앱에서 `dotnet run -- 5`를 사용하여 5까지 계산해 보세요.

> [!IMPORTANT]
> `--` 이후 매개 변수는 `dotnet run` 명령에 전달되지 않고 대신 애플리케이션에 전달됩니다.

## <a name="publish-net-core-app"></a>.NET Core 앱 게시

Docker 이미지에 .NET Core 앱을 추가하기 전에 먼저 앱을 게시해야 합니다. 게시된 버전의 앱을 컨테이너에서 실행하는 것이 가장 좋습니다. 앱을 게시하려면 다음 명령을 실행합니다.

```dotnetcli
dotnet publish -c Release
```

이 명령은 앱을 *publish* 폴더로 컴파일합니다. 작업 폴더에서 *publish* 폴더의 경로는 `.\App\bin\Release\netcoreapp3.1\publish\`이어야 합니다.

#### <a name="windows"></a>[Windows](#tab/windows)

*App* 폴더에서 publish 폴더의 디렉터리 목록을 가져오고 *NetCore.Docker.dll* 파일이 생성되었는지 확인합니다.

```powershell
dir .\bin\Release\netcoreapp3.1\publish\

    Directory: C:\Users\dapine\App\bin\Release\netcoreapp3.1\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[Linux](#tab/linux)

`ls` 명령을 사용하여 디렉터리 목록을 가져오고 *NetCore.Docker.dll* 파일이 생성되었는지 확인합니다.

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a>Dockerfile 만들기

*Dockerfile* 파일은 `docker build` 명령에서 컨테이너 이미지를 만드는 데 사용됩니다. 이 파일은 확장명이 없는 *Dockerfile*이라는 텍스트 파일입니다.

*.csproj*를 포함하는 디렉터리에 *Dockerfile*이라는 파일을 만들고 텍스트 편집기에서 엽니다. 이 자습서에서는 .NET Core 런타임 이미지를 포함하고 .NET Core 콘솔 애플리케이션과 일치하는 ASP.NET Core 런타임 이미지를 사용합니다.

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
```

> [!NOTE]
> `mcr.microsoft.com/dotnet/core/runtime:3.1` 이미지를 사용할 수 있지만 여기서는 의도적으로 ASP.NET Core 런타임 이미지가 사용됩니다.

`FROM` 키워드에는 정규화된 Docker 컨테이너 이미지 이름이 필요합니다. MCR(Microsoft Container Registry, mcr.microsoft.com)은 공개적으로 액세스할 수 있는 컨테이너를 호스트하는 Docker 허브의 신디케이트입니다. `dotnet/core` 세그먼트는 컨테이너 리포지토리입니다. 여기서 `aspnet` 세그먼트는 컨테이너 이미지 이름입니다. 이미지에는 버전 관리에 사용되는 `3.1`태그가 지정됩니다. 따라서 `mcr.microsoft.com/dotnet/core/aspnet:3.1`은 .NET Core 3.1 런타임입니다. SDK에서 대상으로 지정된 런타임과 일치하는 런타임 버전을 풀해야 합니다. 예를 들어 이전 섹션에서 만든 앱은 .NET Core 3.1 SDK를 사용하 고 *Dockerfile*에서 참조하는 기본 이미지에 **3.1** 태그가 지정됩니다.

*Dockerfile* 파일을 저장합니다. 작업 폴더의 디렉터리 구조는 다음과 같이 표시됩니다. 문서에서 공간을 절약하기 위해 더 깊은 수준의 파일과 폴더의 일부가 생략되었습니다.

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──netcoreapp3.1
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

터미널에서 다음 명령을 실행합니다.

```console
docker build -t counter-image -f Dockerfile .
```

Docker가 *Dockerfile*에서 각 줄을 처리합니다. `docker build` 명령의 `.`는 *Dockerfile*을 찾는 데 현재 폴더를 사용하도록 Docker에 지시합니다. 이 명령은 이미지를 빌드하고 해당 이미지를 가리키는 **counter-image**라는 로컬 리포지토리를 만듭니다. 이 명령이 완료된 후 `docker images`를 실행하여 설치된 이미지 목록을 확인합니다.

```console
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

두 이미지가 동일한 **IMAGE ID** 값을 공유함을 알 수 있습니다. *Dockerfile*의 유일한 명령은 기존 이미지를 기반으로 새 이미지를 만드는 것이므로 두 이미지에서 해당 값이 동일합니다. *Dockerfile*에 세 개의 명령을 추가하겠습니다. 각 명령은 **counter-image** 리포지토리 진입점을 나타내는 마지막 명령으로 새 이미지 계층을 만듭니다.

```dockerfile
COPY bin/Release/netcoreapp3.1/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

`COPY` 명령은 컴퓨터의 지정된 폴더를 컨테이너의 폴더에 복사하도록 Docker에 지시합니다. 이 예제에서 *publish* 폴더는 컨테이너의 *App* 폴더에 복사됩니다.

`WORKDIR` 명령은 컨테이너 내부의 **현재 디렉터리**를 *App*으로 변경합니다.

다음 명령인 `ENTRYPOINT`는 컨테이너가 실행 파일로 실행되게 컨테이너를 구성하도록 Docker에 지시합니다. 컨테이너가 시작되면 `ENTRYPOINT` 명령이 실행됩니다. 이 명령이 종료되면 컨테이너가 자동으로 중지됩니다.

터미널에서 `docker build -t counter-image -f Dockerfile .`를 실행하고 명령이 완료되면 `docker images`를 실행합니다.

```console
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> e6780479db63
Step 2/4 : COPY bin/Release/netcoreapp3.1/publish/ App/
 ---> d1732740eed2
Step 3/4 : WORKDIR /App
 ---> Running in b1701a42f3ff
Removing intermediate container b1701a42f3ff
 ---> 919aab5b95e3
Step 4/4 : ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
 ---> Running in c12aebd26ced
Removing intermediate container c12aebd26ced
 ---> cd11c3df9b19
Successfully built cd11c3df9b19
Successfully tagged counter-image:latest

docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              cd11c3df9b19        41 seconds ago      190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

*Dockerfile*의 각 명령이 계층을 생성하고 **IMAGE ID**를 만들었습니다. 마지막 **IMAGE ID**(사용자에 따라 다름)는 **cd11c3df9b19**이고 다음에 이 이미지를 기반으로 컨테이너를 만듭니다.

## <a name="create-a-container"></a>컨테이너 만들기

이제 앱을 포함하는 이미지가 있으므로 컨테이너를 만들 수 있습니다. 두 가지 방법으로 컨테이너를 만들 수 있습니다. 먼저 중지된 새 컨테이너를 만듭니다.

```console
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

위에서 `docker create` 명령은 **counter-image** 이미지를 기반으로 컨테이너를 만듭니다. 해당 명령의 출력은 생성된 컨테이너의 **CONTAINER ID**(사용자에 따라 다름)를 표시합니다. 모든 컨테이너 목록을 보려면 `docker ps -a` 명령을 사용합니다. 

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a>컨테이너 관리

컨테이너는 특정 이름 `core-counter`를 사용하여 만들어졌으며, 이 이름은 컨테이너를 관리하는 데 사용됩니다. 다음 예제에서는 `docker start` 명령을 사용하여 컨테이너를 시작한 후 `docker ps` 명령을 사용하여 실행 중인 컨테이너만 표시합니다.

```console
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

마찬가지로 `docker stop` 명령은 컨테이너를 중지합니다. 다음 예제에서는 `docker stop` 명령을 사용하여 컨테이너를 중지한 다음, `docker ps` 명령을 사용하여 컨테이너가 실행 중이지 않음을 보여 줍니다.

```console
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a>컨테이너에 연결

컨테이너가 실행된 후 컨테이너에 연결하여 출력을 볼 수 있습니다. `docker start` 및 `docker attach` 명령을 사용하여 컨테이너를 시작하고 출력 스트림을 피킹합니다. 이 예제에서는 <kbd>Ctrl+C</kbd> 키 입력을 사용하여 실행 중인 컨테이너에서 분리합니다. 별도로 지정하지 않는 한 이 키 입력은 컨테이너에서 프로세스를 종료하여 컨테이너를 중지합니다. `--sig-proxy=false` 매개 변수를 사용하면 <kbd>Ctrl+C</kbd>가 컨테이너에서 프로세스를 중지합니다.

컨테이너에서 분리한 후 다시 연결하여 계속 실행 및 계산 중인지 확인합니다.

```console
docker start core-counter
core-counter

docker attach --sig-proxy=false core-counter
Counter: 7
Counter: 8
Counter: 9
^C

docker attach --sig-proxy=false core-counter
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>컨테이너 삭제

이 문서의 목적이 아무 작업도 수행하지 않는 컨테이너를 만드는 것은 아닙니다. 이전에 만든 컨테이너를 삭제합니다. 컨테이너가 실행 중이면 중지합니다.

```console
docker stop core-counter
```

다음 예제에는 모든 컨테이너가 나와 있습니다. `docker rm` 명령을 사용하여 컨테이너를 삭제한 후 실행 중인 컨테이너가 있는지 다시 확인합니다.

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a>단일 실행

Docker는 단일 명령으로 컨테이너를 만들고 실행할 수 있는 `docker run` 명령을 제공합니다. 이 명령을 사용하면 `docker create`를 실행한 후 `docker start`를 실행할 필요가 없습니다. 컨테이너가 중지될 때 컨테이너를 자동으로 삭제하도록 이 명령을 설정할 수도 있습니다. 예를 들어 `docker run -it --rm`을 사용하여 두 가지 작업을 수행합니다. 먼저 현재 터미널을 사용하여 컨테이너에 연결한 후 컨테이너가 완료되면 컨테이너를 제거합니다.

```console
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

또한 컨테이너는 .NET Core 앱의 실행에 매개 변수를 전달합니다. .NET Core 앱에 3까지만 계산하도록 지시하려면 3을 전달합니다.

```console
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

`docker run -it`를 사용하면 <kbd>Ctrl+C</kbd> 명령이 컨테이너에서 실행 중인 프로세스를 중지하고, 이에 따라 컨테이너가 중지됩니다. `--rm` 매개 변수가 제공되었으므로 프로세스가 중지되면 컨테이너가 자동으로 삭제됩니다. 컨테이너가 존재하지 않는지 확인합니다.

```console
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a>ENTRYPOINT 변경

`docker run` 명령을 사용하면 *Dockerfile*에서 `ENTRYPOINT` 명령을 수정하고 해당 컨테이너에만 해당하는 다른 작업을 실행할 수 있습니다. 예를 들어 다음 명령을 사용하여 `bash` 또는 `cmd.exe`를 실행합니다. 필요에 따라 명령을 편집합니다.

#### <a name="windows"></a>[Windows](#tab/windows)

이 예제에서 `ENTRYPOINT`는 `cmd.exe`로 변경됩니다. <kbd>Ctrl+C</kbd>를 눌러 프로세스를 종료하고 컨테이너를 중지합니다.

```console
docker run -it --rm --entrypoint "cmd.exe" counter-image

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>[Linux](#tab/linux)

이 예제에서 `ENTRYPOINT`는 `bash`로 변경됩니다. `exit` 명령이 실행되면 프로세스가 종료되고 컨테이너가 중지됩니다.

```bash
docker run -it --rm --entrypoint "bash" counter-image
root@b735b9799abf:/App# ls
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.exe  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
root@b735b9799abf:/App# dotnet NetCore.Docker.dll 3
Counter: 1
Counter: 2
Counter: 3
root@b735b9799abf:/App# exit
exit
```

---

## <a name="essential-commands"></a>필수 명령

Docker에는 컨테이너와 이미지를 만들고, 관리하며, 이와 상호 작용하는 다양한 명령이 있습니다. 이 Docker 명령은 컨테이너 관리에 필수적입니다.

- [docker build](https://docs.docker.com/engine/reference/commandline/build/)
- [docker run](https://docs.docker.com/engine/reference/commandline/run/)
- [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
- [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
- [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
- [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
- [docker image](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a>리소스 정리

이 자습서에서는 컨테이너 및 이미지를 만들었습니다. 원하는 경우 이 리소스를 삭제합니다. 다음 명령을 사용하여 다음을 수행합니다.

01. 모든 컨테이너 나열

    ```console
    docker ps -a
    ```

02. 이름으로 실행 중인 컨테이너를 중지합니다.

    ```console
    docker stop counter-image
    ```

03. 컨테이너 삭제

    ```console
    docker rm counter-image
    ```

그런 다음, 머신에서 더 이상 사용하지 않을 이미지를 삭제합니다. *Dockerfile*에서 만든 이미지를 삭제한 후 *Dockerfile*이 기반으로 하는 .NET Core 이미지를 삭제합니다. **IMAGE ID** 또는 **REPOSITORY:TAG** 형식 문자열을 사용할 수 있습니다.

```console
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

`docker images` 명령을 사용하여 설치된 이미지 목록을 확인합니다.

> [!TIP]
> 이미지 파일이 클 수 있습니다. 일반적으로 앱을 테스트하고 개발하는 동안 만든 임시 컨테이너를 제거합니다. 일반적으로 해당 런타임을 기반으로 다른 이미지를 빌드할 계획인 경우에는 설치된 런타임과 함께 기본 이미지를 유지합니다.

## <a name="next-steps"></a>다음 단계

- [ASP.NET Core 애플리케이션을 컨테이너화하는 방법을 알아봅니다.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [ASP.NET Core 마이크로 서비스 자습서 확인 보기](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [컨테이너를 지원하는 Azure 서비스 검토](https://azure.microsoft.com/overview/containers/)
- [Dockerfile 명령에 대해 읽어 보기](https://docs.docker.com/engine/reference/builder/)
- [Visual studio용 컨테이너 도구 살펴보기](/visualstudio/containers/overview)
