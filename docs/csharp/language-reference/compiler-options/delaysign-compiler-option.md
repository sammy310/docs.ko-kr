---
title: -delaysign(C# 컴파일러 옵션)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 9fdc02c22d9d8c8a709155e43a17ebf0d86dfd69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970440"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="f156a-102">-delaysign(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f156a-102">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="f156a-103">이 옵션을 사용하면 나중에 디지털 시그니처를 추가할 수 있도록 컴파일러가 출력 파일에 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="f156a-104">구문</span><span class="sxs-lookup"><span data-stu-id="f156a-104">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="f156a-105">인수</span><span class="sxs-lookup"><span data-stu-id="f156a-105">Arguments</span></span>

<span data-ttu-id="f156a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f156a-106">`+` &#124; `-`</span></span>

<span data-ttu-id="f156a-107">완전히 서명된 어셈블리가 필요하면 **-delaysign-** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="f156a-108">어셈블리에 공개 키만 배치하려면 **-delaysign+** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="f156a-109">기본값은 **-delaysign-** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-109">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="f156a-110">설명</span><span class="sxs-lookup"><span data-stu-id="f156a-110">Remarks</span></span>

<span data-ttu-id="f156a-111">**-delaysign** 옵션은 [-keyfile](./keyfile-compiler-option.md) 또는 [-keycontainer](./keycontainer-compiler-option.md)와 함께 사용하지 않으면 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-111">The **-delaysign** option has no effect unless used with [-keyfile](./keyfile-compiler-option.md) or [-keycontainer](./keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="f156a-112">**-delaysign** 및 **-publicsign** 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-112">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="f156a-113">완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 프라이빗 키로 해당 해시에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="f156a-114">해당 작업으로 디지털 시그니처가 생생되어 매니페스트가 포함된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-114">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="f156a-115">어셈블리 서명이 연기된 경우 컴파일러는 서명을 컴퓨팅하거나 저장하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-115">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="f156a-116">예를 들어 **-delaysign+** 를 사용하면 테스터를 통해 전역 캐시에 어셈블리를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-116">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="f156a-117">테스트를 마친 후 [어셈블리 링커](../../../framework/tools/al-exe-assembly-linker.md) 유틸리티를 통해 어셈블리에 프라이빗 키를 배치하여 어셈블리에 완전히 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-117">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="f156a-118">자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 및 [어셈블리 서명 지연](../../../standard/assembly/delay-sign.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f156a-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f156a-119">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f156a-119">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="f156a-120">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-120">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="f156a-121">**서명만 연기** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f156a-121">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="f156a-122">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f156a-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="f156a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f156a-123">See also</span></span>

- [<span data-ttu-id="f156a-124">C# -publicsign 옵션</span><span class="sxs-lookup"><span data-stu-id="f156a-124">C# -publicsign option</span></span>](publicsign-compiler-option.md)
- [<span data-ttu-id="f156a-125">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="f156a-125">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="f156a-126">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="f156a-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
