---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132948"
---

<span data-ttu-id="2224c-101">**패키지 {netcore-package}를 찾을 수 없음** 또는 **일부 패키지를 설치할 수 없음**과 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-101">If you receive an error message similar to **Unable to locate package {netcore-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="2224c-102">다음 명령 집합에는 두 개의 자리 표시자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="2224c-103">이는 `aspnetcore-runtime-3.1`와 같이 설치 중인 .NET Core 패키지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="2224c-104">아래의 `sudo apt-get install` 명령에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="2224c-105">현재 사용 중인 Linux 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="2224c-106">아래의 `wget` 명령에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="2224c-107">먼저, 다음 패키지 목록을 제거해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="2224c-108">그런 다음, .NET Core를 다시 설치해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-108">Then, try to install .NET Core again.</span></span> <span data-ttu-id="2224c-109">이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224c-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
