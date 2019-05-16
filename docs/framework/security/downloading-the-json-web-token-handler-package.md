---
title: JSON 웹 토큰 처리기 패키지 다운로드
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: a8685a71d46778d932595965f32c0041b176bd83
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633520"
---
# <a name="download-the-json-web-token-handler-package"></a><span data-ttu-id="26220-102">JSON 웹 토큰 처리기 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="26220-102">Download the JSON Web Token Handler Package</span></span>

<span data-ttu-id="26220-103">이 항목에서는 JSON Web Token 처리기를 다운로드하고 프로젝트에서 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26220-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>

<span data-ttu-id="26220-104">JSON Web Token 처리기 확장은 필요한 어셈블리 및 참조를 프로젝트에 추가하는 NuGet 패키지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26220-104">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="26220-105">NuGet이 아직 설치되지 않은 경우 [nuget.org](https://nuget.org)로 이동하여 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="26220-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="26220-106">NuGet의 해당 페이지를 방문 하 여 확장에 대 한 버전 관리 기록을 확인할 수 있습니다. [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span><span class="sxs-lookup"><span data-stu-id="26220-106">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="26220-107">패키지 관리자 GUI를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="26220-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="26220-108">Visual Studio의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26220-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="26220-109">**NuGet 패키지 관리** 창에서 검색 상자를 클릭하고 `JWT Token Handler`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="26220-109">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>

3. <span data-ttu-id="26220-110">[결과] 창에서 첫 번째 결과에 대한 **설치** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26220-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="26220-111">패키지 다운로드가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="26220-111">The package will begin downloading.</span></span> <span data-ttu-id="26220-112">프로젝트에 추가되기 전에 [라이선스 승인] 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="26220-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="26220-113">사용 약관에 동의하면 **동의**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26220-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="26220-114">최신 JSON Web Token 처리기 어셈블리가 다운로드되고 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="26220-114">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="26220-115">패키지 관리자 콘솔 사용</span><span class="sxs-lookup"><span data-stu-id="26220-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="26220-116">Visual Studio에서 클릭 **도구가** > **NuGet 패키지 관리자** > **패키지 관리자 콘솔**합니다.</span><span class="sxs-lookup"><span data-stu-id="26220-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="26220-117">**패키지 관리자 콘솔**이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="26220-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="26220-118">다음 텍스트를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="26220-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. <span data-ttu-id="26220-119">최신 JSON Web Token 처리기 어셈블리가 다운로드되고 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="26220-119">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>
