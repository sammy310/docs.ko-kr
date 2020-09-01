---
description: -resource(C# 컴파일러 옵션)
title: -resource(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: 963004820f56272b4f1b1d92ccc4d0a60493a4a0
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128701"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="a9dd2-103">-resource(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="a9dd2-103">-resource (C# Compiler Options)</span></span>
<span data-ttu-id="a9dd2-104">출력 파일에 지정된 리소스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-104">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9dd2-105">구문</span><span class="sxs-lookup"><span data-stu-id="a9dd2-105">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a9dd2-106">인수</span><span class="sxs-lookup"><span data-stu-id="a9dd2-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="a9dd2-107">출력 파일에 포함하려는 .NET Framework 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-107">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="a9dd2-108">`identifier`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a9dd2-108">`identifier` (optional)</span></span>  
 <span data-ttu-id="a9dd2-109">리소스의 논리적 이름으로, 리소스를 로드하는 데 사용되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-109">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="a9dd2-110">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-110">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="a9dd2-111">`accessibility-modifier`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a9dd2-111">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="a9dd2-112">리소스의 접근성으로, public 또는 private입니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-112">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="a9dd2-113">기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-113">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9dd2-114">설명</span><span class="sxs-lookup"><span data-stu-id="a9dd2-114">Remarks</span></span>  
 <span data-ttu-id="a9dd2-115">리소스를 어셈블리에 연결하고 출력 파일에 리소스 파일을 추가하지 않으려면 [-linkresource](./linkresource-compiler-option.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-115">Use [-linkresource](./linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="a9dd2-116">기본적으로 리소스는 C# 컴파일러를 사용하여 생성될 때 어셈블리에서 public입니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-116">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="a9dd2-117">리소스를 private로 만들려면 접근성 한정자로 `private`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="a9dd2-118">`public` 또는 `private` 이외의 다른 접근성은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-118">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="a9dd2-119">예를 들어 `filename`이 [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)나 개발 환경에서 만들어진 .NET Framework 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-119">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="a9dd2-120">자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-120">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a9dd2-121">다른 모든 리소스의 경우에는 런타임에 `GetManifestResource` 클래스의 <xref:System.Reflection.Assembly> 메서드를 사용하여 리소스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-121">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="a9dd2-122">**-res**는 **-resource**의 약식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-122">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="a9dd2-123">출력 파일에 있는 리소스의 순서는 명령줄에 지정된 순서에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-123">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a9dd2-124">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a9dd2-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="a9dd2-125">프로젝트에 리소스 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-125">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="a9dd2-126">**솔루션 탐색기**에서 포함할 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-126">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="a9dd2-127">**속성** 창에서 파일에 대한 **빌드 작업**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-127">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="a9dd2-128">**빌드 작업**을 **포함 리소스**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-128">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="a9dd2-129">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.FileProperties2.BuildAction%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-129">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9dd2-130">예제</span><span class="sxs-lookup"><span data-stu-id="a9dd2-130">Example</span></span>  
 <span data-ttu-id="a9dd2-131">`in.cs`를 컴파일하고 리소스 파일 `rf.resource`를 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dd2-131">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9dd2-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9dd2-132">See also</span></span>

- [<span data-ttu-id="a9dd2-133">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="a9dd2-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a9dd2-134">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="a9dd2-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
