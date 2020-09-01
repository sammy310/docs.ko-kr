---
description: -platform(C# 컴파일러 옵션)
title: -platform(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: e2e4fc37418243ff6998d19165250b895c0a4fa1
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124866"
---
# <a name="-platform-c-compiler-options"></a><span data-ttu-id="efac5-103">-platform(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="efac5-103">-platform (C# Compiler Options)</span></span>

<span data-ttu-id="efac5-104">어셈블리를 실행할 수 있는 CLR(공용 언어 런타임) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-104">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>

## <a name="syntax"></a><span data-ttu-id="efac5-105">구문</span><span class="sxs-lookup"><span data-stu-id="efac5-105">Syntax</span></span>

```console
-platform:string
```

## <a name="parameters"></a><span data-ttu-id="efac5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efac5-106">Parameters</span></span>

`string` \
<span data-ttu-id="efac5-107">anycpu(기본값), anycpu32bitpreferred, ARM, x64, x86 또는 Itanium입니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-107">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>

## <a name="remarks"></a><span data-ttu-id="efac5-108">설명</span><span class="sxs-lookup"><span data-stu-id="efac5-108">Remarks</span></span>

- <span data-ttu-id="efac5-109">**anycpu**(기본값)는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-109">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="efac5-110">애플리케이션은 가능할 때마다 64비트로 실행되고 해당 모드를 사용할 수 있을 때만 32비트로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-110">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>

- <span data-ttu-id="efac5-111">**anycpu32bitpreferred**는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-111">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="efac5-112">애플리케이션은 64비트와 32비트 애플리케이션을 모두 지원하는 시스템에서 32비트로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-112">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="efac5-113">.NET Framework 4.5를 대상으로 하는 프로젝트에 대해서만 이 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-113">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>

- <span data-ttu-id="efac5-114">**ARM**은 ARM(고급 RISC 컴퓨터) 프로세서가 있는 컴퓨터에서 실행할 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-114">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>

- <span data-ttu-id="efac5-115">**ARM64**는 A64 명령 집합을 지원하는 ARM(고급 RISC 머신) 프로세서가 있는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-115">**ARM64** compiles your assembly to run by the 64-bit CLR on a computer that has an Advanced RISC Machine (ARM) processor that supports the A64 instruction set.</span></span>

- <span data-ttu-id="efac5-116">**x64**는 AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-116">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>

- <span data-ttu-id="efac5-117">**x86**은 32비트, x86 호환 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-117">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>

- <span data-ttu-id="efac5-118">**Itanium**은 Itanium 프로세서 탑재 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-118">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>

<span data-ttu-id="efac5-119">64비트 Windows 운영 체제:</span><span class="sxs-lookup"><span data-stu-id="efac5-119">On a 64-bit Windows operating system:</span></span>

- <span data-ttu-id="efac5-120">**-platform:x86**으로 컴파일된 어셈블리는 WOW64에서 실행되는 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-120">Assemblies compiled with **-platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>

- <span data-ttu-id="efac5-121">**-platform:anycpu**로 컴파일된 DLL은 이 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-121">A DLL compiled with the **-platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>

- <span data-ttu-id="efac5-122">**-platform:anycpu**로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-122">Executables that are compiled with the **-platform:anycpu** execute on the 64-bit CLR.</span></span>

- <span data-ttu-id="efac5-123">**-platform:anycpu32bitpreferred**로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-123">Executables compiled with **-platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>

<span data-ttu-id="efac5-124">**anycpu32bitpreferred** 설정은 실행 파일(.EXE)에 대해서만 유효하고 .NET Framework 4.5를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-124">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>

<span data-ttu-id="efac5-125">Windows 64비트 운영 체제에서 실행할 애플리케이션을 개발하는 방법에 대한 자세한 내용은 [64비트 애플리케이션](../../../framework/64-bit-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efac5-125">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="efac5-126">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="efac5-126">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="efac5-127">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-127">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="efac5-128">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-128">Click the **Build** property page.</span></span>

3. <span data-ttu-id="efac5-129">.NET Framework 4.5를 대상으로 하는 프로젝트에 대해 **플랫폼 대상** 속성을 수정하고 **32비트 선호** 확인란을 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-129">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>

> [!NOTE]
> <span data-ttu-id="efac5-130">`-platform`은 Visual C# Express의 개발 환경에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-130">`-platform` is not available in the development environment in Visual C# Express.</span></span>

<span data-ttu-id="efac5-131">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efac5-131">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>

## <a name="example"></a><span data-ttu-id="efac5-132">예제</span><span class="sxs-lookup"><span data-stu-id="efac5-132">Example</span></span>

<span data-ttu-id="efac5-133">다음 예제에서는 **-platform** 옵션을 사용하여 애플리케이션이 64비트 Windows 운영 체제의 64비트 CLR에서만 실행되도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efac5-133">The following example shows how to use the **-platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>

```console
csc -platform:anycpu filename.cs
```

## <a name="see-also"></a><span data-ttu-id="efac5-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efac5-134">See also</span></span>

- [<span data-ttu-id="efac5-135">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="efac5-135">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="efac5-136">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="efac5-136">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
