---
description: -delaysign(C# 컴파일러 옵션)
title: -delaysign(C# 컴파일러 옵션)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 5512ebeca4672f5d69852ab07c3f3fa40c305327
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125841"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="fe2b2-103">-delaysign(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="fe2b2-103">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="fe2b2-104">이 옵션을 사용하면 나중에 디지털 시그니처를 추가할 수 있도록 컴파일러가 출력 파일에 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-104">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="fe2b2-105">구문</span><span class="sxs-lookup"><span data-stu-id="fe2b2-105">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="fe2b2-106">인수</span><span class="sxs-lookup"><span data-stu-id="fe2b2-106">Arguments</span></span>

<span data-ttu-id="fe2b2-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fe2b2-107">`+` &#124; `-`</span></span>

<span data-ttu-id="fe2b2-108">완전히 서명된 어셈블리가 필요하면 **-delaysign-** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-108">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="fe2b2-109">어셈블리에 공개 키만 배치하려면 **-delaysign+** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-109">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="fe2b2-110">기본값은 **-delaysign-** 입니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-110">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe2b2-111">설명</span><span class="sxs-lookup"><span data-stu-id="fe2b2-111">Remarks</span></span>

<span data-ttu-id="fe2b2-112">**-delaysign** 옵션은 [-keyfile](./keyfile-compiler-option.md) 또는 [-keycontainer](./keycontainer-compiler-option.md)와 함께 사용하지 않으면 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-112">The **-delaysign** option has no effect unless used with [-keyfile](./keyfile-compiler-option.md) or [-keycontainer](./keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="fe2b2-113">**-delaysign** 및 **-publicsign** 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-113">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="fe2b2-114">완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 프라이빗 키로 해당 해시에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-114">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="fe2b2-115">해당 작업으로 디지털 시그니처가 생생되어 매니페스트가 포함된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-115">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="fe2b2-116">어셈블리 서명이 연기된 경우 컴파일러는 서명을 컴퓨팅하거나 저장하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-116">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="fe2b2-117">예를 들어 **-delaysign+** 를 사용하면 테스터를 통해 전역 캐시에 어셈블리를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-117">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="fe2b2-118">테스트를 마친 후 [어셈블리 링커](../../../framework/tools/al-exe-assembly-linker.md) 유틸리티를 통해 어셈블리에 프라이빗 키를 배치하여 어셈블리에 완전히 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-118">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="fe2b2-119">자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 및 [어셈블리 서명 지연](../../../standard/assembly/delay-sign.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-119">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="fe2b2-120">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fe2b2-120">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="fe2b2-121">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-121">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="fe2b2-122">**서명만 연기** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-122">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="fe2b2-123">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe2b2-123">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe2b2-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe2b2-124">See also</span></span>

- [<span data-ttu-id="fe2b2-125">C# -publicsign 옵션</span><span class="sxs-lookup"><span data-stu-id="fe2b2-125">C# -publicsign option</span></span>](publicsign-compiler-option.md)
- [<span data-ttu-id="fe2b2-126">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="fe2b2-126">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="fe2b2-127">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="fe2b2-127">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
