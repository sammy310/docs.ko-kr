---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506985"
---

<span data-ttu-id="136f5-101">**{netcore-package} 패키지를 찾을 수 없음** 또는 **일부 패키지를 설치할 수 없음** 과 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-101">If you receive an error message similar to **Unable to locate package {dotnet-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="136f5-102">다음 명령 집합에는 두 개의 자리 표시자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="136f5-103">`aspnetcore-runtime-3.1`과 같이 설치 중인 .NET 패키지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-103">This represents the .NET package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="136f5-104">다음 `sudo apt-get install` 명령에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-104">This is used in the following `sudo apt-get install` command.</span></span>

- `{os-version}`\
<span data-ttu-id="136f5-105">현재 사용 중인 Linux 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="136f5-106">아래의 `wget` 명령에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="136f5-107">먼저, 다음 패키지 목록을 제거해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="136f5-108">그런 다음, .NET을 다시 설치해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-108">Then, try to install .NET again.</span></span> <span data-ttu-id="136f5-109">이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="136f5-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
