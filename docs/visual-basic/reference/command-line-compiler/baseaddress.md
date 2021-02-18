---
description: '자세한 정보: -baseaddress'
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
ms.openlocfilehash: eaa2992c126ebb83b20cfdbef3ab995a30ee25fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468319"
---
# <a name="-baseaddress"></a><span data-ttu-id="d1e0f-103">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="d1e0f-103">-baseaddress</span></span>

<span data-ttu-id="d1e0f-104">DLL을 만들 때 기본 기준 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-104">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e0f-105">구문</span><span class="sxs-lookup"><span data-stu-id="d1e0f-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1e0f-106">인수</span><span class="sxs-lookup"><span data-stu-id="d1e0f-106">Arguments</span></span>  
  
|<span data-ttu-id="d1e0f-107">용어</span><span class="sxs-lookup"><span data-stu-id="d1e0f-107">Term</span></span>|<span data-ttu-id="d1e0f-108">정의</span><span class="sxs-lookup"><span data-stu-id="d1e0f-108">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="d1e0f-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-109">Required.</span></span> <span data-ttu-id="d1e0f-110">DLL의 기준 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-110">The base address for the DLL.</span></span> <span data-ttu-id="d1e0f-111">이 주소는 16진수 숫자로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-111">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1e0f-112">설명</span><span class="sxs-lookup"><span data-stu-id="d1e0f-112">Remarks</span></span>  

 <span data-ttu-id="d1e0f-113">DLL에 대한 기본 기준 주소는 .NET Framework에 의해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-113">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="d1e0f-114">이 주소의 하위 단어는 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-114">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="d1e0f-115">예를 들어 0x11110001을 지정하면 0x11110000으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-115">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="d1e0f-116">DLL에 대한 서명 프로세스를 완료하려면 강력한 이름 지정 도구(Sn.exe)의 `–R` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-116">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="d1e0f-117">대상이 DLL이 아닌 경우이 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-117">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="d1e0f-118">Visual Studio IDE에서 -baseaddress를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d1e0f-118">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="d1e0f-119">1.  **솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d1e0f-120">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d1e0f-121">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d1e0f-122">3.  **고급** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="d1e0f-123">4.  **DLL 기준 주소:** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="d1e0f-124">**참고:**      대상이 DLL이 아닌 한 **DLL 기준 주소:** 상자는 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e0f-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1e0f-125">참조</span><span class="sxs-lookup"><span data-stu-id="d1e0f-125">See also</span></span>

- [<span data-ttu-id="d1e0f-126">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d1e0f-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d1e0f-127">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1e0f-127">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="d1e0f-128">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="d1e0f-128">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="d1e0f-129">[Sn.exe(강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)</span><span class="sxs-lookup"><span data-stu-id="d1e0f-129">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
