---
ms.openlocfilehash: 5a027054024d8429831d73525ab3748c51ae850e
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255760"
---

<span data-ttu-id="2503d-101">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2503d-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="2503d-102">그러나, .NET Core를 수동으로 설치하거나 자체 포함된 앱을 게시할 경우 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2503d-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="2503d-103">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="2503d-103">krb5-libs</span></span>
- <span data-ttu-id="2503d-104">libicu</span><span class="sxs-lookup"><span data-stu-id="2503d-104">libicu</span></span>
- <span data-ttu-id="2503d-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="2503d-105">openssl-libs</span></span>
- <span data-ttu-id="2503d-106">zlib</span><span class="sxs-lookup"><span data-stu-id="2503d-106">zlib</span></span>

<span data-ttu-id="2503d-107">대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10** 을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2503d-107">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="2503d-108">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2503d-108">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="2503d-109">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2503d-109">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="2503d-110">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="2503d-110">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="2503d-111">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2503d-111">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="2503d-112">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2503d-112">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
