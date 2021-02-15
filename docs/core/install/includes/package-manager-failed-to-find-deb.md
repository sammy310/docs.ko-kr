---
ms.openlocfilehash: 3275865cf7f4669ba7deaacea320136d02f64dda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804238"
---

<span data-ttu-id="0afb9-101">**{netcore-package} 패키지를 찾을 수 없음** 또는 **일부 패키지를 설치할 수 없음** 과 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-101">If you receive an error message similar to **Unable to locate package {dotnet-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="0afb9-102">다음 명령 집합에는 두 개의 자리 표시자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="0afb9-103">`aspnetcore-runtime-3.1`과 같이 설치 중인 .NET 패키지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-103">This represents the .NET package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="0afb9-104">다음 `sudo apt-get install` 명령에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-104">This is used in the following `sudo apt-get install` command.</span></span>

- `{os-version}`\
<span data-ttu-id="0afb9-105">이는 현재 배포 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-105">This represents the distribution version you're on.</span></span> <span data-ttu-id="0afb9-106">아래의 `wget` 명령에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-106">This is used in the `wget` command below.</span></span> <span data-ttu-id="0afb9-107">배포 버전은 Ubuntu의 `20.04` 또는 Debian의 `10`과 같은 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-107">The distribution version is the numerical value, such as `20.04` on Ubuntu or `10` on Debian.</span></span>

<span data-ttu-id="0afb9-108">먼저, 다음 패키지 목록을 제거해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-108">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="0afb9-109">그런 다음, .NET을 다시 설치해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-109">Then, try to install .NET again.</span></span> <span data-ttu-id="0afb9-110">이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afb9-110">If that doesn't work, you can run a manual install with the following commands:</span></span>
