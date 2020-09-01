---
description: -linkresource(C# 컴파일러 옵션)
title: -linkresource(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: 162baad57397b6d992dcf8f03f0b3661e0105cb8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125347"
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="4afc6-103">-linkresource(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="4afc6-103">-linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="4afc6-104">출력 파일에 .NET Framework 리소스에 대한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-104">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="4afc6-105">리소스 파일은 출력 파일에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-105">The resource file is not added to the output file.</span></span> <span data-ttu-id="4afc6-106">이 점에서 출력 파일에 리소스 파일을 포함하는 [-resource](./resource-compiler-option.md) 옵션과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-106">This differs from the [-resource](./resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4afc6-107">구문</span><span class="sxs-lookup"><span data-stu-id="4afc6-107">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4afc6-108">인수</span><span class="sxs-lookup"><span data-stu-id="4afc6-108">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="4afc6-109">어셈블리에서 연결할 .NET Framework 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-109">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="4afc6-110">`identifier`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="4afc6-110">`identifier` (optional)</span></span>  
 <span data-ttu-id="4afc6-111">리소스의 논리적 이름으로, 리소스를 로드하는 데 사용되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-111">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="4afc6-112">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-112">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="4afc6-113">`accessibility-modifier`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="4afc6-113">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="4afc6-114">리소스의 접근성으로, public 또는 private입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-114">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="4afc6-115">기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-115">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4afc6-116">설명</span><span class="sxs-lookup"><span data-stu-id="4afc6-116">Remarks</span></span>  
 <span data-ttu-id="4afc6-117">기본적으로 연결된 리소스는 C# 컴파일러로 생성될 때 어셈블리에서 public입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-117">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="4afc6-118">리소스를 private로 만들려면 접근성 한정자로 `private`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-118">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="4afc6-119">`public` 또는 `private` 이외의 다른 한정자는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-119">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="4afc6-120">**-linkresource**에는 **-target:module** 이외의 [-target](./target-compiler-option.md) 옵션 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-120">**-linkresource** requires one of the [-target](./target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="4afc6-121">예를 들어 `filename`이 [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)나 개발 환경에서 만들어진 .NET Framework 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-121">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="4afc6-122">자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4afc6-122">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4afc6-123">다른 모든 리소스의 경우에는 런타임에 `GetManifestResource` 클래스의 <xref:System.Reflection.Assembly> 메서드를 사용하여 리소스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-123">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="4afc6-124">`filename`에 지정된 파일은 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-124">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="4afc6-125">예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-125">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="4afc6-126">다음 중 두 번째 예제에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-126">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="4afc6-127">어셈블리 링커에서도 동일한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-127">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="4afc6-128">다음 중 세 번째 예제에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-128">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="4afc6-129">자세한 내용은 [Al.exe(어셈블리 링커)](../../../framework/tools/al-exe-assembly-linker.md) 및 [어셈블리 및 전역 어셈블리 캐시 사용](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4afc6-129">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="4afc6-130">**-linkres**는 **-linkresource**의 약식입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-130">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="4afc6-131">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-131">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4afc6-132">예제</span><span class="sxs-lookup"><span data-stu-id="4afc6-132">Example</span></span>  
 <span data-ttu-id="4afc6-133">`in.cs`를 컴파일하고 리소스 파일 `rf.resource`에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-133">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="4afc6-134">예제</span><span class="sxs-lookup"><span data-stu-id="4afc6-134">Example</span></span>  
 <span data-ttu-id="4afc6-135">`A.cs`를 DLL로 컴파일하고, 네이티브 DLL N.dll에 연결한 다음 출력을 GAC(전역 어셈블리 캐시)에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-135">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="4afc6-136">이 예제에서는 A.dll과 N.dll이 둘 다 GAC에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-136">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="4afc6-137">예제</span><span class="sxs-lookup"><span data-stu-id="4afc6-137">Example</span></span>  
 <span data-ttu-id="4afc6-138">이 예제에서는 앞의 예제와 동일한 작업을 수행하지만 어셈블리 링커 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4afc6-138">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="4afc6-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4afc6-139">See also</span></span>

- [<span data-ttu-id="4afc6-140">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="4afc6-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4afc6-141">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="4afc6-141">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="4afc6-142">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="4afc6-142">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="4afc6-143">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="4afc6-143">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
