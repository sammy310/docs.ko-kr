---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: ccf569aea1363d256728e122818b70284a9e250d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830372"
---
# <a name="-delaysign"></a><span data-ttu-id="e896a-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="e896a-102">-delaysign</span></span>
<span data-ttu-id="e896a-103">어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e896a-104">구문</span><span class="sxs-lookup"><span data-stu-id="e896a-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e896a-105">인수</span><span class="sxs-lookup"><span data-stu-id="e896a-105">Arguments</span></span>  
 <span data-ttu-id="e896a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e896a-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="e896a-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-107">Optional.</span></span> <span data-ttu-id="e896a-108">어셈블리에 완전히 서명하려면 `-delaysign-`를 사용하고</span><span class="sxs-lookup"><span data-stu-id="e896a-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="e896a-109">사용 하 여 `-delaysign+` 부호 있는 해시에 대 한 어셈블리 및 예약 공간에 공개 키를 저장 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="e896a-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="e896a-110">기본값은 `-delaysign-`입니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e896a-111">설명</span><span class="sxs-lookup"><span data-stu-id="e896a-111">Remarks</span></span>  
 <span data-ttu-id="e896a-112">합니다 `-delaysign` 옵션은 사용 하지 않는 한 효과가 없습니다 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 하거나 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="e896a-113">완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 개인 키로 해당 해시에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="e896a-114">결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="e896a-115">어셈블리 서명이 연기 되 면 컴파일러 계산 하거나 나중에 서명을 추가할 수 있도록 파일에 서명 하지만 예약 공간을 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="e896a-116">사용 하 여 예를 들어 `-delaysign+`, 조직에서 개발자 테스터가 어셈블리를 전역 어셈블리 캐시를 사용 하 여 등록 하 고 사용할 수 있는 어셈블리의 서명 되지 않은 테스트 버전을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="e896a-117">어셈블리에 대 한 작업 완료 되 면 담당자는 조직의 개인 키를 어셈블리에 완전히 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="e896a-118">이 작업은 모든 개발자는 어셈블리의 작업을 허용 하는 동안 공개에서 조직의 개인 키를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="e896a-119">참조 [강력한 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="e896a-120">Visual Studio 통합된 개발 환경에서-delaysign을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e896a-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="e896a-121">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e896a-122">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-122">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="e896a-123">**시그니처** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-123">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="e896a-124">값을 설정 합니다 **서명만 연기** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="e896a-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e896a-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="e896a-125">See also</span></span>

- [<span data-ttu-id="e896a-126">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="e896a-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e896a-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="e896a-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="e896a-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="e896a-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [<span data-ttu-id="e896a-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="e896a-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
