---
title: Clrver.exe(CLR 버전 도구)
description: Clrver.exe 즉, CLR 버전 도구를 검토합니다. 이 도구는 컴퓨터에 있는 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: 0787cdf09d55a8464db7f5495b5aeed52c22f5d4
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104654182"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="c2aa2-104">Clrver.exe(CLR 버전 도구)</span><span class="sxs-lookup"><span data-stu-id="c2aa2-104">Clrver.exe (CLR Version Tool)</span></span>

<span data-ttu-id="c2aa2-105">CLR 버전 도구(Clrver.exe)에서는 컴퓨터에서 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-105">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="c2aa2-106">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c2aa2-107">도구를 실행하려면 [Visual Studio 개발자 명령 프롬프트 또는 Visual Studio 개발자 PowerShell](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-107">To run the tool, use [Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="c2aa2-108">명령 프롬프트에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-108">At the command prompt, enter the following command:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2aa2-109">구문</span><span class="sxs-lookup"><span data-stu-id="c2aa2-109">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="c2aa2-110">옵션</span><span class="sxs-lookup"><span data-stu-id="c2aa2-110">Options</span></span>  
  
|<span data-ttu-id="c2aa2-111">옵션</span><span class="sxs-lookup"><span data-stu-id="c2aa2-111">Option</span></span>|<span data-ttu-id="c2aa2-112">Description</span><span class="sxs-lookup"><span data-stu-id="c2aa2-112">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="c2aa2-113">CLR을 사용 중인 컴퓨터에 모든 프로세스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-113">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="c2aa2-114">*pid*</span><span class="sxs-lookup"><span data-stu-id="c2aa2-114">*pid*</span></span>|<span data-ttu-id="c2aa2-115">지정한 프로세스 ID(PID)를 가진 프로세스에서 사용하는 CLR의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-115">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="c2aa2-116">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-116">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2aa2-117">설명</span><span class="sxs-lookup"><span data-stu-id="c2aa2-117">Remarks</span></span>  

 <span data-ttu-id="c2aa2-118">옵션 없이 Clrver.exe를 호출하는 경우 설치된 모든 CLR 버전이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-118">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="c2aa2-119">다른 사용자에 대한 PID를 지정할 경우 버전 정보를 얻으려면 관리 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-119">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2aa2-120">Windows Vista 이상에서는 UAC(사용자 계정 컨트롤)가 사용자 권한을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-120">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="c2aa2-121">기본 제공 Administrators 그룹의 멤버인 경우 두 개의 런타임 액세스 토큰(표준 사용자 액세스 토큰 및 관리자 액세스 토큰)이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-121">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="c2aa2-122">기본적으로 표준 사용자 역할이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-122">By default, you are in the standard user role.</span></span> <span data-ttu-id="c2aa2-123">관리 권한이 필요한 코드를 실행하려면 먼저 표준 사용자에서 관리자로 권한을 높여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-123">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="c2aa2-124">명령 프롬프트 아이콘을 마우스 오른쪽 단추로 클릭하고 관리자로 실행하도록 지정하여 명령 프롬프트를 시작하면 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-124">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="c2aa2-125">SYSTEM, LOCAL SERVICE 및 NETWORK SERVICE 프로세스에 대한 CLR 버전을 확인하려고 시도하면 PID가 존재하지 않는다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-125">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c2aa2-126">예</span><span class="sxs-lookup"><span data-stu-id="c2aa2-126">Examples</span></span>  

 <span data-ttu-id="c2aa2-127">다음 명령은 컴퓨터에 설치된 CLR의 모든 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-127">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="c2aa2-128">다음 명령은 프로세스 128에서 사용하는 CLR의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-128">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="c2aa2-129">다음 명령은 관리되는 모든 프로세스와 이들이 사용하는 CLR의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2aa2-129">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="c2aa2-130">참조</span><span class="sxs-lookup"><span data-stu-id="c2aa2-130">See also</span></span>

- [<span data-ttu-id="c2aa2-131">도구</span><span class="sxs-lookup"><span data-stu-id="c2aa2-131">Tools</span></span>](index.md)
- [<span data-ttu-id="c2aa2-132">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="c2aa2-132">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
