---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002394"
---
# <a name="-baseaddress"></a><span data-ttu-id="9166f-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="9166f-102">-baseaddress</span></span>
<span data-ttu-id="9166f-103">DLL을 만들 때 기본 기준 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9166f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9166f-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="9166f-105">인수</span><span class="sxs-lookup"><span data-stu-id="9166f-105">Arguments</span></span>  
  
|<span data-ttu-id="9166f-106">용어</span><span class="sxs-lookup"><span data-stu-id="9166f-106">Term</span></span>|<span data-ttu-id="9166f-107">정의</span><span class="sxs-lookup"><span data-stu-id="9166f-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="9166f-108">필수.</span><span class="sxs-lookup"><span data-stu-id="9166f-108">Required.</span></span> <span data-ttu-id="9166f-109">DLL의 기준 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-109">The base address for the DLL.</span></span> <span data-ttu-id="9166f-110">이 주소는 16 진수 숫자로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9166f-111">설명</span><span class="sxs-lookup"><span data-stu-id="9166f-111">Remarks</span></span>  
 <span data-ttu-id="9166f-112">DLL에 대 한 기본 기준 주소는 .NET Framework에 의해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="9166f-113">이 주소의 하위 단어는 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="9166f-114">예를 들어 0x11110001를 지정 하면 0x11110000로 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="9166f-115">DLL에 대 한 서명 프로세스를 완료 하려면 강력한 이름 지정 도구 (Sn.exe)의 `–R` 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="9166f-116">대상이 DLL이 아닌 경우이 옵션은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="9166f-117">Visual Studio IDE에서 baseaddress로 설정</span><span class="sxs-lookup"><span data-stu-id="9166f-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="9166f-118">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9166f-119">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="9166f-120">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="9166f-121">3.  **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="9166f-122">4.  **DLL 기준 주소:** 상자에서 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="9166f-123">**참고:**      대상이 DLL이 아닌 경우에는 **dll 기준 주소:** 상자는 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="9166f-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9166f-124">참조</span><span class="sxs-lookup"><span data-stu-id="9166f-124">See also</span></span>

- [<span data-ttu-id="9166f-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9166f-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9166f-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9166f-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="9166f-127">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="9166f-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="9166f-128">[Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="9166f-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
