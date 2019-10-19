---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 3ee94df096b756be544964cfbbd405355e3f728f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581267"
---
# <a name="-delaysign"></a><span data-ttu-id="58a91-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="58a91-102">-delaysign</span></span>

<span data-ttu-id="58a91-103">어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-103">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="58a91-104">구문</span><span class="sxs-lookup"><span data-stu-id="58a91-104">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="58a91-105">인수</span><span class="sxs-lookup"><span data-stu-id="58a91-105">Arguments</span></span>

<span data-ttu-id="58a91-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="58a91-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="58a91-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="58a91-107">Optional.</span></span> <span data-ttu-id="58a91-108">어셈블리에 완전히 서명하려면 `-delaysign-`를 사용하고</span><span class="sxs-lookup"><span data-stu-id="58a91-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="58a91-109">어셈블리에 공개 키를 추가 하 고 서명 된 해시의 공간을 예약 하려면 `-delaysign+`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="58a91-110">기본값은 `-delaysign-`입니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-110">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="58a91-111">주의</span><span class="sxs-lookup"><span data-stu-id="58a91-111">Remarks</span></span>

<span data-ttu-id="58a91-112">@No__t_0 옵션은 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 또는 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)와 함께 사용 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>

<span data-ttu-id="58a91-113">완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 프라이빗 키로 해당 해시에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="58a91-114">결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="58a91-115">어셈블리의 서명이 연기 된 경우 컴파일러는 서명을 계산 및 저장 하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="58a91-116">예를 들어 `-delaysign+`를 사용 하 여 조직의 개발자는 테스터가 전역 어셈블리 캐시에 등록 하 고 사용할 수 있는 어셈블리의 서명 되지 않은 테스트 버전을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="58a91-117">어셈블리에 대 한 작업이 완료 되 면 조직의 개인 키를 담당 하는 사람이 어셈블리에 완전히 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="58a91-118">이 compartmentalization는 조직의 개인 키를 공개 하지 않도록 보호 하는 동시에 모든 개발자가 어셈블리를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="58a91-119">어셈블리 서명에 대 한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58a91-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="58a91-120">Visual Studio 통합 개발 환경에서 delaysign로 설정</span><span class="sxs-lookup"><span data-stu-id="58a91-120">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="58a91-121">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="58a91-122">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-122">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="58a91-123">**시그니처** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-123">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="58a91-124">**서명 연기** 상자에서 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58a91-124">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="58a91-125">참조</span><span class="sxs-lookup"><span data-stu-id="58a91-125">See also</span></span>

- [<span data-ttu-id="58a91-126">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="58a91-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="58a91-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="58a91-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="58a91-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="58a91-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [<span data-ttu-id="58a91-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="58a91-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
