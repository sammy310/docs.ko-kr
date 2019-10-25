---
title: '연습: Visual Studio에 관리되는 어셈블리의 형식 포함'
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1a37a3bcc3b1bc352d6a2f59691819e0b2403d3d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523902"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="9df09-102">연습: Visual Studio에 관리되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="9df09-102">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="9df09-103">강력한 이름의 관리되는 어셈블리에서 형식 정보를 포함하는 경우 애플리케이션에서 유형을 느슨하게 연결하여 버전 독립성을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="9df09-104">즉, 새로운 버전마다 다시 컴파일하지 않고도 관리되는 라이브러리의 모든 버전에서 형식을 사용하도록 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-104">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="9df09-105">형식 포함은 Microsoft Office의 자동화 개체를 사용하는 애플리케이션과 같은 COM interop에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="9df09-106">형식 정보를 포함하면 서로 다른 컴퓨터의 서로 다른 Microsoft Office 버전에서 동일한 빌드의 프로그램을 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="9df09-107">그러나 완전 관리형 솔루션에서도 형식 포함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-107">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="9df09-108">포함할 수 있는 공용 인터페이스를 지정한 후 이러한 인터페이스를 구현하는 런타임 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-108">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="9df09-109">클라이언트 프로그램은 공용 인터페이스가 포함된 어셈블리를 참조하고 참조의 `Embed Interop Types` 속성을 `True`로 설정하여 디자인 타임에 해당 인터페이스의 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-109">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="9df09-110">그러면 클라이언트 프로그램은 해당 인터페이스로 형식이 지정된 런타임 개체의 인스턴스를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-110">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="9df09-111">이는 명령줄 컴파일러를 사용하고 `/link` 컴파일러 옵션을 사용하여 어셈블리를 참조하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-111">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> 

<span data-ttu-id="9df09-112">강력한 이름의 런타임 어셈블리의 새 버전을 만들면 클라이언트 프로그램을 다시 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-112">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="9df09-113">클라이언트 프로그램은 공용 인터페이스의 포함된 형식 정보를 통해 사용 가능한 런타임 어셈블리 버전을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-113">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="9df09-114">이 연습에서는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-114">In this walkthrough, you:</span></span>

1. <span data-ttu-id="9df09-115">포함할 수 있는 형식 정보가 있는 공개 인터페이스와 함께 강력한 이름의 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-115">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="9df09-116">공용 인터페이스를 구현하는 강력한 이름의 런타임 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-116">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="9df09-117">공용 인터페이스에서 형식 정보를 포함하고 런타임 어셈블리에서 클래스의 인스턴스를 만드는 클라이언트 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-117">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="9df09-118">런타임 어셈블리를 수정하고 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-118">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="9df09-119">클라이언트 프로그램을 실행하면 다시 컴파일하지 않고도 클라이언트 프로그램이 런타임 어셈블리의 새 버전을 사용하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-119">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="9df09-120">조건 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="9df09-120">Conditions and limitations</span></span>

<span data-ttu-id="9df09-121">다음 조건에서는 어셈블리의 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-121">You can embed type information from an assembly under the following conditions:</span></span> 

- <span data-ttu-id="9df09-122">어셈블리는 하나 이상의 공용 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-122">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="9df09-123">포함된 인터페이스는 고유한 GUID가 있는 `ComImport` 특성 및 `Guid` 특성으로 주석이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-123">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="9df09-124">어셈블리는 `ImportedFromTypeLib` 특성이나 `PrimaryInteropAssembly` 특성, 그리고 어셈블리 수준의 `Guid` 특성으로 주석이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-124">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="9df09-125">Visual C# 및 Visual Basic 프로젝트 템플릿에는 기본적으로 어셈블리 수준의 `Guid` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-125">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="9df09-126">형식 포함의 기본 기능은 COM interop 어셈블리를 지원하는 것이므로 완전 관리형 솔루션에 형식 정보를 포함할 때 다음과 같은 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-126">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="9df09-127">COM interop 관련 특성만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-127">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="9df09-128">다른 특성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-128">Other attributes are ignored.</span></span>
- <span data-ttu-id="9df09-129">형식이 제네릭 매개 변수를 사용하고 제네릭 매개 변수의 형식이 포함된 형식인 경우 해당 형식을 어셈블리 경계를 넘어 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-129">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="9df09-130">어셈블리 경계를 넘어가는 예로는 다른 어셈블리에서 메서드를 호출하는 경우 또는 다른 어셈블리에 정의된 형식에서 형식이 파생되는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-130">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="9df09-131">상수는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-131">Constants are not embedded.</span></span>
- <span data-ttu-id="9df09-132"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> 클래스는 포함된 형식을 키로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-132">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="9df09-133">포함된 형식을 키로서 지원하도록 고유한 사전 형식을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-133">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="9df09-134">인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="9df09-134">Create an interface</span></span>

<span data-ttu-id="9df09-135">첫 번째 단계는 형식 동등 인터페이스 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-135">The first step is to create the type equivalence interface assembly.</span></span> 

1. <span data-ttu-id="9df09-136">Visual Studio에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-136">In Visual Studio, select **File** > **New** > **Project**.</span></span>
   
1. <span data-ttu-id="9df09-137">**새 프로젝트 만들기** 대화 상자에서 **템플릿 검색** 상자에 *class library*를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-137">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="9df09-138">목록에서 C# 또는 VB **클래스 라이브러리(.NET Framework)** 템플릿을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-138">Select either the C# or VB **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span> 
   
1. <span data-ttu-id="9df09-139">**새 프로젝트 구성** 대화 상자에서 **프로젝트 이름**에 *TypeEquivalenceInterface*를 입력한 다음 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-139">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="9df09-140">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-140">The new project is created.</span></span>
   
1. <span data-ttu-id="9df09-141">**솔루션 탐색기**에서 *Class1.cs* 또는 *Class1.vb* 파일을 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기**를 선택하여 파일 이름을 *Class1*에서 *ISampleInterface*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-141">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="9df09-142">클래스의 이름도 `ISampleInterface`로 바꿀지 묻는 메시지가 표시되면 **예**라고 답합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-142">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="9df09-143">이 클래스는 클래스의 공용 인터페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-143">This class represents the public interface for the class.</span></span>
   
1. <span data-ttu-id="9df09-144">**솔루션 탐색기**에서 **TypeEquivalenceInterface** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-144">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span> 
   
1. <span data-ttu-id="9df09-145">**속성** 화면의 왼쪽 창에서 **빌드**를 선택하고 **출력 경로**를 *C:\TypeEquivalenceSample* 같은 컴퓨터의 위치로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-145">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="9df09-146">이 연습 전체에서 동일한 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-146">You use the same location throughout this walkthrough.</span></span> 
   
1. <span data-ttu-id="9df09-147">**속성** 화면의 왼쪽 창에서 **서명**을 선택한 다음 **어셈블리에 서명** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-147">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="9df09-148">**강력한 이름 키 파일 선택** 드롭다운 목록에서 **새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-148">In the dropdown for **Choose a strong name key file**, select **New**.</span></span> 
   
1. <span data-ttu-id="9df09-149">**강력한 이름 키 만들기** 대화 상자의 **키 파일 이름**에 *key.snk*를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-149">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="9df09-150">**암호로 내 키 파일 보호** 확인란의 선택을 취소한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-150">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>
   
1. <span data-ttu-id="9df09-151">코드 편집기에서 *ISampleInterface* 클래스를 열고 콘텐츠를 다음 코드로 바꾸어 `ISampleInterface` 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-151">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>
   
   ```csharp
   using System;
   using System.Runtime.InteropServices;
   
   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```
   
   ```vb
   Imports System.Runtime.InteropServices
   
   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```
   
1. <span data-ttu-id="9df09-152">**도구** 메뉴에서 **GUID 만들기**를 선택하고 **GUID 만들기** 대화 상자에서 **레지스트리 형식**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-152">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="9df09-153">**복사**를 선택한 다음 **끝내기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-153">Select **Copy**, and then select **Exit**.</span></span>
   
1. <span data-ttu-id="9df09-154">코드의 `Guid` 특성에서 샘플 GUID를 복사한 GUID로 바꾸고 중괄호( **{ }** )를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-154">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>
   
1. <span data-ttu-id="9df09-155">**솔루션 탐색기**에서 **속성** 폴더를 펼치고 *AssemblyInfo.cs* 또는 *AssemblyInfo.vb* 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-155">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="9df09-156">코드 편집기에서 파일에 다음 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-156">In the code editor, add the following attribute to the file:</span></span>
   
   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```
   
   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```
   
1. <span data-ttu-id="9df09-157">**파일** > **모두 저장**을 선택하거나 **Ctrl**+**Shift**+**S**를 눌러 파일과 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-157">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="9df09-158">**솔루션 탐색기**에서 **TypeEquivalenceInterface** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-158">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="9df09-159">클래스 라이브러리 DLL 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다(예: *C:\TypeEquivalenceSample*).</span><span class="sxs-lookup"><span data-stu-id="9df09-159">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="9df09-160">런타임 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="9df09-160">Create a runtime class</span></span>

<span data-ttu-id="9df09-161">다음으로 동등한 형식의 런타임 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-161">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="9df09-162">Visual Studio에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-162">In Visual Studio, select **File** > **New** > **Project**.</span></span>
   
1. <span data-ttu-id="9df09-163">**새 프로젝트 만들기** 대화 상자에서 **템플릿 검색** 상자에 *class library*를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-163">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="9df09-164">목록에서 C# 또는 VB **클래스 라이브러리(.NET Framework)** 템플릿을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-164">Select either the C# or VB **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span> 
   
1. <span data-ttu-id="9df09-165">**새 프로젝트 구성** 대화 상자에서 **프로젝트 이름**에 *TypeEquivalenceRuntime*을 입력한 다음 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-165">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="9df09-166">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-166">The new project is created.</span></span>
   
1. <span data-ttu-id="9df09-167">**솔루션 탐색기**에서 *Class1.cs* 또는 *Class1.vb* 파일을 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기**를 선택하여 파일 이름을 *Class1*에서 *SampleClass*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-167">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="9df09-168">클래스의 이름도 `SampleClass`로 바꿀지 묻는 메시지가 표시되면 **예**라고 답합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-168">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="9df09-169">이 클래스는 `ISampleInterface` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-169">This class implements the `ISampleInterface` interface.</span></span>
   
1. <span data-ttu-id="9df09-170">**솔루션 탐색기**에서 **TypeEquivalenceInterface** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-170">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="9df09-171">**속성** 화면 왼쪽 창에서 **빌드**를 선택한 다음 **출력 경로**를 TypeEquivalenceInterface 프로젝트에 사용한 것과 동일한 위치로 설정합니다(예: *C:\TypeEquivalenceSample*).</span><span class="sxs-lookup"><span data-stu-id="9df09-171">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>
   
1. <span data-ttu-id="9df09-172">**속성** 화면의 왼쪽 창에서 **서명**을 선택한 다음 **어셈블리에 서명** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-172">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="9df09-173">**강력한 이름 키 파일 선택** 드롭다운 목록에서 **새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-173">In the dropdown for **Choose a strong name key file**, select **New**.</span></span> 
   
1. <span data-ttu-id="9df09-174">**강력한 이름 키 만들기** 대화 상자의 **키 파일 이름**에 *key.snk*를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-174">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="9df09-175">**암호로 내 키 파일 보호** 확인란의 선택을 취소한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-175">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>
   
1. <span data-ttu-id="9df09-176">**솔루션 탐색기**에서 **TypeEquivalenceRuntime** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **참조**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-176">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span> 
   
1. <span data-ttu-id="9df09-177">**참조 관리자** 대화 상자에서 **찾아보기**를 선택하고 출력 경로 폴더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-177">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="9df09-178">*TypeEquivalenceInterface.dll* 파일을 선택하고 **추가**를 선택한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-178">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>
   
1. <span data-ttu-id="9df09-179">**솔루션 탐색기**에서 **참조** 폴더를 펼치고 **TypeEquivalenceInterface** 참조를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-179">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="9df09-180">**속성** 창에서 아직 설정하지 않았다면 **특정 버전**을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-180">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>
   
1. <span data-ttu-id="9df09-181">코드 편집기에서 *SampleClass* 클래스 파일을 열고 콘텐츠를 다음 코드로 바꾸어 `SampleClass` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-181">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>
   
   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;
   using System.Text;
   using TypeEquivalenceInterface;
   
   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }
   
           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```
   
   ```vb
   Imports TypeEquivalenceInterface
   
   Public Class SampleClass
       Implements ISampleInterface
   
       Private p_UserInput As String
       Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
           Get
               Return p_UserInput
           End Get
       End Property
   
       Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
           Console.WriteLine("Please enter a value:")
           p_UserInput = Console.ReadLine()
       End Sub
   End Class
   ```
   
1. <span data-ttu-id="9df09-182">**파일** > **모두 저장**을 선택하거나 **Ctrl**+**Shift**+**S**를 눌러 파일과 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-182">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="9df09-183">**솔루션 탐색기**에서 **TypeEquivalenceRuntime** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-183">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="9df09-184">클래스 라이브러리 DLL 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-184">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="9df09-185">클라이언트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9df09-185">Create a client project</span></span>

<span data-ttu-id="9df09-186">마지막으로 인터페이스 어셈블리를 참조하는 형식 동등 클라이언트 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-186">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="9df09-187">Visual Studio에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-187">In Visual Studio, select **File** > **New** > **Project**.</span></span>
   
1. <span data-ttu-id="9df09-188">**새 프로젝트 만들기** 대화 상자에서 **템플릿 검색** 상자에 *console*을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-188">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="9df09-189">목록에서 C# 또는 VB **콘솔 앱(.NET Framework)** 템플릿을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-189">Select either the C# or VB **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span> 
   
1. <span data-ttu-id="9df09-190">**새 프로젝트 구성** 대화 상자에서 **프로젝트 이름**에 *TypeEquivalenceClient*를 입력한 다음 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-190">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="9df09-191">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-191">The new project is created.</span></span>
   
1. <span data-ttu-id="9df09-192">**솔루션 탐색기**에서 **TypeEquivalenceClient** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-192">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="9df09-193">**속성** 화면 왼쪽 창에서 **빌드**를 선택한 다음 **출력 경로**를 TypeEquivalenceInterface 프로젝트에 사용한 것과 동일한 위치로 설정합니다(예: *C:\TypeEquivalenceSample*).</span><span class="sxs-lookup"><span data-stu-id="9df09-193">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>
   
1. <span data-ttu-id="9df09-194">**솔루션 탐색기**에서 **TypeEquivalenceClient** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **참조**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span> 
   
1. <span data-ttu-id="9df09-195">**참조 관리자** 대화 상자에서 **TypeEquivalenceInterface.dll** 파일이 이미 나열되어 있다면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-195">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="9df09-196">그렇지 않다면 **찾아보기**를 선택해 출력 경로 폴더를 찾고, *TypeEquivalenceInterface.dll* 파일( *TypeEquivalenceRuntime.dll*이 아님)을 선택하고 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-196">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="9df09-197">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-197">Select **OK**.</span></span>
   
1. <span data-ttu-id="9df09-198">**솔루션 탐색기**에서 **참조** 폴더를 펼치고 **TypeEquivalenceInterface** 참조를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-198">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="9df09-199">**속성** 창에서 **Interop 형식 포함**을 **True**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-199">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>
   
1. <span data-ttu-id="9df09-200">코드 편집기에서 *Program.cs* 또는 *Module1.vb* 파일을 열고 콘텐츠를 다음 코드로 바꾸어 클라이언트 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-200">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>
   
   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;
   using System.Text;
   using TypeEquivalenceInterface;
   using System.Reflection;
   
   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```
   
   ```vb
   Imports TypeEquivalenceInterface
   Imports System.Reflection
   
   Module Module1
   
       Sub Main()
           Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
           Dim sampleClass As ISampleInterface = CType( _
               sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
           sampleClass.GetUserInput()
           Console.WriteLine(sampleClass.UserInput)
           Console.WriteLine(sampleAssembly.GetName().Version)
           Console.ReadLine()
       End Sub
   
   End Module
   ```
   
1. <span data-ttu-id="9df09-201">**파일** > **모두 저장**을 선택하거나 **Ctrl**+**Shift**+**S**를 눌러 파일과 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-201">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="9df09-202">**Ctrl**+**F5**를 눌러 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-202">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="9df09-203">콘솔 출력은 어셈블리 버전 **1.0.0.0**을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-203">Note that the console output returns the assembly version **1.0.0.0**.</span></span> 
   
## <a name="modify-the-interface"></a><span data-ttu-id="9df09-204">인터페이스 수정</span><span class="sxs-lookup"><span data-stu-id="9df09-204">Modify the interface</span></span>

<span data-ttu-id="9df09-205">이제 인터페이스 어셈블리를 수정하고 해당 버전을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-205">Now, modify the interface assembly, and change its version.</span></span> 

1. <span data-ttu-id="9df09-206">Visual Studio에서 **파일** > **열기** > **프로젝트/솔루션**을 선택하고 **TypeEquivalenceInterface** 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-206">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>
   
1. <span data-ttu-id="9df09-207">**솔루션 탐색기**에서 **TypeEquivalenceInterface** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-207">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="9df09-208">**속성** 화면의 왼쪽 창에서 **애플리케이션**을 선택한 다음 **어셈블리 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-208">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span> 
   
1. <span data-ttu-id="9df09-209">**어셈블리 정보** 대화 상자에서 **어셈블리 버전** 및 **파일 버전** 값을 *2.0.0.0*으로 변경한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-209">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>
   
1. <span data-ttu-id="9df09-210">*SampleInterface.cs* 또는 *SampleInterface.vb* 파일을 열고 다음 코드 줄을 `ISampleInterface` 인터페이스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-210">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>
   
   ```csharp
   DateTime GetDate();
   ```
   
   ```vb
   Function GetDate() As Date
   ```
   
1. <span data-ttu-id="9df09-211">**파일** > **모두 저장**을 선택하거나 **Ctrl**+**Shift**+**S**를 눌러 파일과 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-211">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="9df09-212">**솔루션 탐색기**에서 **TypeEquivalenceInterface** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-212">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="9df09-213">새 버전의 클래스 라이브러리 DLL 파일이 컴파일되고 빌드 출력 경로에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-213">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="9df09-214">런타임 클래스 수정</span><span class="sxs-lookup"><span data-stu-id="9df09-214">Modify the runtime class</span></span>

<span data-ttu-id="9df09-215">또한 런타임 클래스를 수정하고 해당 버전을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-215">Also modify the runtime class and update its version.</span></span> 

1. <span data-ttu-id="9df09-216">Visual Studio에서 **파일** > **열기** > **프로젝트/솔루션**을 선택하고 **TypeEquivalenceRuntime** 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-216">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>
   
1. <span data-ttu-id="9df09-217">**솔루션 탐색기**에서 **TypeEquivalenceRuntime** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-217">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="9df09-218">**속성** 화면의 왼쪽 창에서 **애플리케이션**을 선택한 다음 **어셈블리 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-218">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span> 
   
1. <span data-ttu-id="9df09-219">**어셈블리 정보** 대화 상자에서 **어셈블리 버전** 및 **파일 버전** 값을 *2.0.0.0*으로 변경한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-219">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>
   
1. <span data-ttu-id="9df09-220">*SampleClass.cs* 또는 *SampleClass.vb* 파일을 열고 다음 코드를 `SampleClass` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-220">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>
   
   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```
   
   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```
   
1. <span data-ttu-id="9df09-221">**파일** > **모두 저장**을 선택하거나 **Ctrl**+**Shift**+**S**를 눌러 파일과 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-221">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="9df09-222">**솔루션 탐색기**에서 **TypeEquivalenceRuntime** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-222">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="9df09-223">새 버전의 클래스 라이브러리 DLL 파일이 컴파일되고 빌드 출력 경로에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-223">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="9df09-224">업데이트된 클라이언트 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="9df09-224">Run the updated client program</span></span> 

<span data-ttu-id="9df09-225">빌드 출력 폴더 위치로 이동하여 *TypeEquivalenceClient.exe*를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-225">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="9df09-226">이제 프로그램을 다시 컴파일하지 않고도 콘솔 출력에 `TypeEquivalenceRuntime` 어셈블리의 새 버전 *2.0.0.0*이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="9df09-226">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="9df09-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9df09-227">See also</span></span>

- [<span data-ttu-id="9df09-228">-link(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="9df09-228">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="9df09-229">-link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9df09-229">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="9df09-230">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9df09-230">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9df09-231">프로그래밍 개념(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9df09-231">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="9df09-232">어셈블리를 사용한 프로그램</span><span class="sxs-lookup"><span data-stu-id="9df09-232">Program with assemblies</span></span>](program.md)
- [<span data-ttu-id="9df09-233">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="9df09-233">Assemblies in .NET</span></span>](index.md)
