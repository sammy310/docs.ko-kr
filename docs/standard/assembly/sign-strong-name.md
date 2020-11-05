---
title: '방법: 강력한 이름으로 어셈블리 서명'
description: 이 문서에서는 서명 탭, 어셈블리 링커, 어셈블리 특성 또는 컴파일러 옵션을 사용하여 강력한 이름으로 .NET 어셈블리에 서명하는 방법을 보여 줍니다.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET], signing
- assemblies [.NET], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 5192f7f372b9ef7927930c3599aebc6fca9f1f0f
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687655"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="b583c-103">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="b583c-103">How to: Sign an assembly with a strong name</span></span>

> [!NOTE]
> <span data-ttu-id="b583c-104">.NET Core가 강력한 이름의 어셈블리를 지원하고 .NET Core 라이브러리의 모든 어셈블리는 서명되어 있지만 대부분의 타사 어셈블리에는 강력한 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-104">Although .NET Core supports strong-named assemblies, and all assemblies in the .NET Core library are signed, the majority of third-party assemblies do not need strong names.</span></span> <span data-ttu-id="b583c-105">자세한 내용은 GitHub의 [강력한 이름 서명](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b583c-105">For more information, see [Strong Name Signing](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) on GitHub.</span></span>

<span data-ttu-id="b583c-106">강력한 이름으로 어셈블리에 서명하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-106">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
- <span data-ttu-id="b583c-107">Visual Studio에서 프로젝트의 **속성** 대화 상자에서 **서명** 탭을 사용하는 방법.</span><span class="sxs-lookup"><span data-stu-id="b583c-107">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="b583c-108">이는 가장 쉽고 편리하게 강력한 이름으로 어셈블리에 서명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-108">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
- <span data-ttu-id="b583c-109">[어셈블리 링커(Al.exe)](../../framework/tools/al-exe-assembly-linker.md)를 사용하여 .NET Framework 코드 모듈( *.netmodule* 파일)을 키 파일과 연결하는 방법.</span><span class="sxs-lookup"><span data-stu-id="b583c-109">By using the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a *.netmodule* file) with a key file.</span></span>  
  
- <span data-ttu-id="b583c-110">어셈블리 특성을 사용하여 강력한 이름 정보를 코드에 삽입하는 방법.</span><span class="sxs-lookup"><span data-stu-id="b583c-110">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="b583c-111">사용할 키 파일의 위치에 따라 <xref:System.Reflection.AssemblyKeyFileAttribute> 또는 <xref:System.Reflection.AssemblyKeyNameAttribute> 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-111">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
- <span data-ttu-id="b583c-112">컴파일러 옵션을 사용하는 방법.</span><span class="sxs-lookup"><span data-stu-id="b583c-112">By using compiler options.</span></span>  
  
 <span data-ttu-id="b583c-113">강력한 이름으로 어셈블리를 서명하려면 암호화 키 쌍이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-113">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="b583c-114">키 쌍을 만드는 방법에 대한 자세한 내용은 [방법: 퍼블릭/프라이빗 키 쌍 만들기](create-public-private-key-pair.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b583c-114">For more information about creating a key pair, see [How to: Create a public-private key pair](create-public-private-key-pair.md).</span></span>  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="b583c-115">Visual Studio를 사용하여 강력한 이름으로 어셈블리를 만들고 서명</span><span class="sxs-lookup"><span data-stu-id="b583c-115">Create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="b583c-116">**솔루션 탐색기** 에서 프로젝트의 바로 가기 메뉴를 열고 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-116">In **Solution Explorer** , open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="b583c-117">**서명** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-117">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="b583c-118">**어셈블리 서명** 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-118">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="b583c-119">**강력한 이름 키 파일 선택** 상자에서 **찾아보기** 를 선택한 다음 키 파일로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-119">In the **Choose a strong name key file** box, choose **Browse** , and then navigate to the key file.</span></span> <span data-ttu-id="b583c-120">새 키 파일을 만들려면 **새로 만들기** 를 선택하고 **강력한 이름 키 만들기** 대화 상자에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-120">To create a new key file, choose **New** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b583c-121">[어셈블리를 지연 서명](delay-sign.md)하기 위해 공개 키 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-121">In order to [delay sign an assembly](delay-sign.md), choose a public key file.</span></span>  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="b583c-122">어셈블리 링커를 사용하여 강력한 이름으로 어셈블리를 만들고 서명</span><span class="sxs-lookup"><span data-stu-id="b583c-122">Create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
<span data-ttu-id="b583c-123">[Visual Studio용 개발자 명령 프롬프트](../../framework/tools/developer-command-prompt-for-vs.md)에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-123">At the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), enter the following command:</span></span>  

<span data-ttu-id="b583c-124">**al** **/out:** \<*assemblyName*> *\<moduleName>* **/keyfile:** \<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="b583c-124">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  

<span data-ttu-id="b583c-125">여기서</span><span class="sxs-lookup"><span data-stu-id="b583c-125">Where:</span></span>  

- <span data-ttu-id="b583c-126">*assemblyName* 은 어셈블리 링커가 내보낼 강력하게 서명된 어셈블리( *.dll* 또는 *.exe* 파일)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-126">*assemblyName* is the name of the strongly signed assembly (a *.dll* or *.exe* file) that Assembly Linker will emit.</span></span>  
  
- <span data-ttu-id="b583c-127">*moduleName* 은 하나 이상의 형식을 포함하는 .NET Framework 코드 모듈( *.netmodule* 파일)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-127">*moduleName* is the name of a .NET Framework code module (a *.netmodule* file) that includes one or more types.</span></span> <span data-ttu-id="b583c-128">C# 또는 Visual Basic에서 `/target:module` 스위치로 코드를 컴파일하여 *.netmodule* 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-128">You can create a *.netmodule* file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>
  
- <span data-ttu-id="b583c-129">*keyfileName* 은 키 쌍을 포함하는 컨테이너 또는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-129">*keyfileName* is the name of the container or file that contains the key pair.</span></span> <span data-ttu-id="b583c-130">어셈블리 링커는 현재 디렉터리를 기준으로 상대 경로를 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-130">Assembly Linker interprets a relative path in relation to the current directory.</span></span>  

<span data-ttu-id="b583c-131">다음 예제에서는 키 쌍 파일 *sgKey.snk* 를 사용하여 강력한 이름으로 *MyAssembly.dll* 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-131">The following example signs the assembly *MyAssembly.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
<span data-ttu-id="b583c-132">이 도구에 대한 자세한 내용은 [어셈블리 링커](../../framework/tools/al-exe-assembly-linker.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b583c-132">For more information about this tool, see [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span></span>  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="b583c-133">특성을 사용하여 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="b583c-133">Sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="b583c-134"><xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> 또는 <xref:System.Reflection.AssemblyKeyNameAttribute> 특성을 소스 코드 모듈에 추가하고, 강력한 이름으로 어셈블리를 서명할 때 사용할 키 쌍이 포함된 컨테이너 또는 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-134">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  

2. <span data-ttu-id="b583c-135">소스 코드 파일을 정상적으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-135">Compile the source code file normally.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="b583c-136">C# 및 Visual Basic 컴파일러에서는 소스 코드에 <xref:System.Reflection.AssemblyKeyFileAttribute> 또는 <xref:System.Reflection.AssemblyKeyNameAttribute> 특성이 나올 때 컴파일러 경고(각각 CS1699 및 BC41008)를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-136">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="b583c-137">이런 경고는 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-137">You can ignore the warnings.</span></span>  

<span data-ttu-id="b583c-138">다음 예제에서는 어셈블리가 컴파일된 디렉터리에 있는 *keyfile.snk* 라는 키 파일과 함께 <xref:System.Reflection.AssemblyKeyFileAttribute> 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-138">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called *keyfile.snk* , which is located in the directory where the assembly is compiled.</span></span>  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

<span data-ttu-id="b583c-139">또한, 소스 파일을 컴파일할 때 어셈블리 서명을 연기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-139">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="b583c-140">자세한 내용은 [어셈블리 지연 서명](delay-sign.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b583c-140">For more information, see [Delay-sign an assembly](delay-sign.md).</span></span>  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="b583c-141">컴파일러를 사용하여 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="b583c-141">Sign an assembly with a strong name by using the compiler</span></span>  

<span data-ttu-id="b583c-142">C# 및 Visual Basic 컴파일러에서 `/keyfile` 또는 `/delaysign` 컴파일러 옵션을 사용하거나 C++에서 `/KEYFILE` 또는 `/DELAYSIGN` 링커 옵션을 사용하여 소스 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-142">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="b583c-143">옵션 이름 다음에 콜론과 키 파일의 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-143">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="b583c-144">명령줄 컴파일러를 사용할 때, 소스 코드 파일이 포함된 디렉터리에 키 파일을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-144">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  

<span data-ttu-id="b583c-145">지연 서명에 대한 자세한 내용은 [어셈블리 지연 서명](delay-sign.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b583c-145">For information on delay signing, see [Delay-sign an assembly](delay-sign.md).</span></span>  

<span data-ttu-id="b583c-146">다음 예제에서는 C# 컴파일러를 사용하고 키 파일 *sgKey.snk* 를 사용하여 강력한 이름으로 *UtilityLibrary.dll* 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="b583c-146">The following example uses the C# compiler and signs the assembly *UtilityLibrary.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a><span data-ttu-id="b583c-147">참조</span><span class="sxs-lookup"><span data-stu-id="b583c-147">See also</span></span>

- [<span data-ttu-id="b583c-148">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="b583c-148">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="b583c-149">방법: 퍼블릭/프라이빗 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="b583c-149">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="b583c-150">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="b583c-150">Al.exe (Assembly Linker)</span></span>](../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="b583c-151">어셈블리 지연 서명</span><span class="sxs-lookup"><span data-stu-id="b583c-151">Delay-sign an assembly</span></span>](delay-sign.md)
- [<span data-ttu-id="b583c-152">어셈블리 및 매니페스트 서명 관리</span><span class="sxs-lookup"><span data-stu-id="b583c-152">Manage assembly and manifest signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="b583c-153">서명 페이지, 프로젝트 디자이너</span><span class="sxs-lookup"><span data-stu-id="b583c-153">Signing page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
