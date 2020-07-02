---
title: '방법: 글로벌 어셈블리 캐시에 어셈블리 설치'
description: 여러 애플리케이션에서 공유할 수 있도록 어셈블리를 .NET의 GAC(전역 어셈블리 캐시)에 설치합니다. Windows Installer 또는 GAC 유틸리티를 사용합니다.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 08a5475d74327265f28b65676ae56be15afb57d3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104665"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="ebdba-104">방법: 글로벌 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="ebdba-104">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="ebdba-105">GAC(글로벌 어셈블리 캐시)는 여러 애플리케이션이 공유하는 어셈블리를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-105">The global assembly cache (GAC) stores assemblies that several applications share.</span></span> <span data-ttu-id="ebdba-106">다음 구성 요소 중 하나를 사용하여 [글로벌 어셈블리 캐시](gac.md)에 어셈블리를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-106">Install an assembly into the [global assembly cache](gac.md) with one of the following components:</span></span>

- [<span data-ttu-id="ebdba-107">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="ebdba-107">Windows Installer</span></span>](#windows-installer)
- [<span data-ttu-id="ebdba-108">전역 어셈블리 캐시 도구</span><span class="sxs-lookup"><span data-stu-id="ebdba-108">Global Assembly Cache tool</span></span>](#global-assembly-cache-tool)

> [!IMPORTANT]
> <span data-ttu-id="ebdba-109">강력한 이름의 어셈블리만 전역 어셈블리 캐시에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-109">You can install only strong-named assemblies into the global assembly cache.</span></span> <span data-ttu-id="ebdba-110">강력한 이름의 어셈블리를 만드는 방법에 대한 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../standard/assembly/sign-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebdba-110">For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="ebdba-111">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="ebdba-111">Windows Installer</span></span>

<span data-ttu-id="ebdba-112">Windows 설치 엔진인 [Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache)는 전역 어셈블리 캐시에 어셈블리를 추가하는 권장 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-112">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="ebdba-113">Windows Installer는 전역 어셈블리 캐시의 어셈블리 참조 횟수 및 다른 여러 가지 혜택을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-113">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="ebdba-114">Windows Installer용 설치 관리자 패키지를 만들려면 [Visual Studio 2017용 WiX Toolset 확장](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ebdba-114">To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="ebdba-115">전역 어셈블리 캐시 도구</span><span class="sxs-lookup"><span data-stu-id="ebdba-115">Global Assembly Cache tool</span></span>

<span data-ttu-id="ebdba-116">[.NET 전역 어셈블리 캐시 유틸리티(gacutil.exe)](../tools/gacutil-exe-gac-tool.md)를 사용하여 어셈블리를 전역 어셈블리 캐시에 추가하고 전역 어셈블리 캐시의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-116">You can use the [.NET Global Assembly Cache utility (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ebdba-117">*Gacutil.exe*는 개발 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-117">*Gacutil.exe* is for development purposes only.</span></span> <span data-ttu-id="ebdba-118">해당 파일을 사용하여 프로덕션 어셈블리를 글로벌 어셈블리 캐시에 설치하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ebdba-118">Don't use it to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="ebdba-119">GAC에 어셈블리를 설치하기 위해 *gacutil.exe*를 사용하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-119">The syntax for using *gacutil.exe* to install an assembly in the GAC is as follows:</span></span>

```cmd
gacutil -i <assembly name>
```

<span data-ttu-id="ebdba-120">이 명령에서 *\<assembly name>* 은 전역 어셈블리 캐시에 설치할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-120">In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="ebdba-121">*gacutil.exe*가 시스템 경로에 없는 경우 [VS *\<version>* 용 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-121">If *gacutil.exe* isn't in your system path, use the [Developer command prompt for VS *\<version>*](../tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="ebdba-122">다음 예제는 파일 이름이 *hello.dll*인 어셈블리를 글로벌 어셈블리 캐시에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-122">The following example installs an assembly with the file name *hello.dll* into the global assembly cache.</span></span>

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="ebdba-123">이전 버전의 .NET Framework에서는 *Shfusion.dll* Windows 셸 확장을 통해 파일 탐색기로 어셈블리를 끌어와서 설치할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-123">In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension let you install assemblies by dragging them to File Explorer.</span></span> <span data-ttu-id="ebdba-124">.NET Framework 4부터는 *Shfusion.dll*이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdba-124">Beginning with .NET Framework 4, *Shfusion.dll* is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebdba-125">참조</span><span class="sxs-lookup"><span data-stu-id="ebdba-125">See also</span></span>

- [<span data-ttu-id="ebdba-126">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="ebdba-126">Work with assemblies and the global assembly cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="ebdba-127">방법: 글로벌 어셈블리 캐시에서 어셈블리 제거</span><span class="sxs-lookup"><span data-stu-id="ebdba-127">How to: Remove an assembly from the global assembly cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="ebdba-128">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="ebdba-128">Gacutil.exe (Global Assembly Cache tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="ebdba-129">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="ebdba-129">How to: Sign an assembly with a strong name</span></span>](../../standard/assembly/sign-strong-name.md)
