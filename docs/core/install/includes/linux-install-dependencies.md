---
ms.openlocfilehash: b371525c9f4e57c6a09e5bb9232884e5c5e707e0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602767"
---

<span data-ttu-id="307de-101">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="307de-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="307de-102">그러나, .NET Core를 수동으로 설치하거나 자체 포함된 앱을 게시할 경우 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="307de-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="307de-103">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="307de-103">lttng-ust</span></span>
- <span data-ttu-id="307de-104">libcurl</span><span class="sxs-lookup"><span data-stu-id="307de-104">libcurl</span></span>
- <span data-ttu-id="307de-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="307de-105">openssl-libs</span></span>
- <span data-ttu-id="307de-106">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="307de-106">krb5-libs</span></span>
- <span data-ttu-id="307de-107">libicu</span><span class="sxs-lookup"><span data-stu-id="307de-107">libicu</span></span>
- <span data-ttu-id="307de-108">zlib</span><span class="sxs-lookup"><span data-stu-id="307de-108">zlib</span></span>
- <span data-ttu-id="307de-109">libunwind</span><span class="sxs-lookup"><span data-stu-id="307de-109">libunwind</span></span>
- <span data-ttu-id="307de-110">libuuid</span><span class="sxs-lookup"><span data-stu-id="307de-110">libuuid</span></span>

<span data-ttu-id="307de-111">대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10**을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="307de-111">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="307de-112">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="307de-112">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="307de-113">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="307de-113">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="307de-114">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="307de-114">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="307de-115">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus*를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307de-115">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="307de-116">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="307de-116">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
