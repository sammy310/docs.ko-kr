---
title: Clrver.exe(CLR 버전 도구)
description: Clrver.exe 즉, CLR 버전 도구를 검토합니다. 이 도구는 컴퓨터에 있는 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: 3a7a585d990051553aa8fdc0e99b2dc206273cf4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247228"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="904a2-104">Clrver.exe(CLR 버전 도구)</span><span class="sxs-lookup"><span data-stu-id="904a2-104">Clrver.exe (CLR Version Tool)</span></span>

<span data-ttu-id="904a2-105">CLR 버전 도구(Clrver.exe)에서는 컴퓨터에서 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-105">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="904a2-106">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="904a2-107">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="904a2-108">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="904a2-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="904a2-109">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="904a2-110">구문</span><span class="sxs-lookup"><span data-stu-id="904a2-110">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="904a2-111">옵션</span><span class="sxs-lookup"><span data-stu-id="904a2-111">Options</span></span>  
  
|<span data-ttu-id="904a2-112">옵션</span><span class="sxs-lookup"><span data-stu-id="904a2-112">Option</span></span>|<span data-ttu-id="904a2-113">Description</span><span class="sxs-lookup"><span data-stu-id="904a2-113">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="904a2-114">CLR을 사용 중인 컴퓨터에 모든 프로세스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-114">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="904a2-115">*pid*</span><span class="sxs-lookup"><span data-stu-id="904a2-115">*pid*</span></span>|<span data-ttu-id="904a2-116">지정한 프로세스 ID(PID)를 가진 프로세스에서 사용하는 CLR의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-116">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="904a2-117">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-117">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="904a2-118">설명</span><span class="sxs-lookup"><span data-stu-id="904a2-118">Remarks</span></span>  

 <span data-ttu-id="904a2-119">옵션 없이 Clrver.exe를 호출하는 경우 설치된 모든 CLR 버전이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-119">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="904a2-120">다른 사용자에 대한 PID를 지정할 경우 버전 정보를 얻으려면 관리 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-120">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="904a2-121">Windows Vista 이상에서는 UAC(사용자 계정 컨트롤)가 사용자 권한을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-121">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="904a2-122">기본 제공 Administrators 그룹의 멤버인 경우 두 개의 런타임 액세스 토큰(표준 사용자 액세스 토큰 및 관리자 액세스 토큰)이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-122">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="904a2-123">기본적으로 표준 사용자 역할이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-123">By default, you are in the standard user role.</span></span> <span data-ttu-id="904a2-124">관리 권한이 필요한 코드를 실행하려면 먼저 표준 사용자에서 관리자로 권한을 높여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-124">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="904a2-125">명령 프롬프트 아이콘을 마우스 오른쪽 단추로 클릭하고 관리자로 실행하도록 지정하여 명령 프롬프트를 시작하면 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-125">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="904a2-126">SYSTEM, LOCAL SERVICE 및 NETWORK SERVICE 프로세스에 대한 CLR 버전을 확인하려고 시도하면 PID가 존재하지 않는다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-126">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="904a2-127">예</span><span class="sxs-lookup"><span data-stu-id="904a2-127">Examples</span></span>  

 <span data-ttu-id="904a2-128">다음 명령은 컴퓨터에 설치된 CLR의 모든 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-128">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="904a2-129">다음 명령은 프로세스 128에서 사용하는 CLR의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-129">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="904a2-130">다음 명령은 관리되는 모든 프로세스와 이들이 사용하는 CLR의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="904a2-130">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="904a2-131">참조</span><span class="sxs-lookup"><span data-stu-id="904a2-131">See also</span></span>

- [<span data-ttu-id="904a2-132">도구</span><span class="sxs-lookup"><span data-stu-id="904a2-132">Tools</span></span>](index.md)
- [<span data-ttu-id="904a2-133">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="904a2-133">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
