---
title: '방법: 지역화된 예외 메시지를 사용하여 사용자 정의 예외 생성'
description: '방법: 지역화된 예외 메시지를 사용하여 사용자 정의 예외 만드는 방법 알아보기'
author: Youssef1313
dev_langs:
- csharp
- vb
ms.date: 09/13/2019
ms.openlocfilehash: fa0bbfdbfc9408302eec2edd4e4ee4503d2612c7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243351"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a><span data-ttu-id="30751-103">방법: 지역화된 예외 메시지를 사용하여 사용자 정의 예외 생성</span><span class="sxs-lookup"><span data-stu-id="30751-103">How to create user-defined exceptions with localized exception messages</span></span>

<span data-ttu-id="30751-104">이 문서에서는 위성 어셈블리를 사용하여 지역화된 예외 메시지로 기본 <xref:System.Exception> 클래스에서 상속되는 사용자 정의 예외를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-104">In this article, you will learn how to create user-defined exceptions that are inherited from the base <xref:System.Exception> class with localized exception messages using satellite assemblies.</span></span>

## <a name="create-custom-exceptions"></a><span data-ttu-id="30751-105">사용자 지정 예외 만들기</span><span class="sxs-lookup"><span data-stu-id="30751-105">Create custom exceptions</span></span>

<span data-ttu-id="30751-106">.NET에는 사용할 수 있는 다양한 예외가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30751-106">.NET contains many different exceptions that you can use.</span></span> <span data-ttu-id="30751-107">그러나 사용자의 요구를 충족하는 항목이 없는 경우에는 사용자 지정 예외를 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30751-107">However, in some cases when none of them meets your needs, you can create your own custom exceptions.</span></span>

<span data-ttu-id="30751-108">`StudentName` 속성을 포함하는 `StudentNotFoundException`을 만들려고 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="30751-108">Let's assume you want to create a `StudentNotFoundException` that contains a `StudentName` property.</span></span>
<span data-ttu-id="30751-109">사용자 지정 예외를 만들려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-109">To create a custom exception, follow these steps:</span></span>

1. <span data-ttu-id="30751-110"><xref:System.Exception>에서 상속된 serializable 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30751-110">Create a serializable class that inherits from <xref:System.Exception>.</span></span> <span data-ttu-id="30751-111">클래스 이름은 "Exception"으로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-111">The class name should end in "Exception":</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception
    End Class
    ```

1. <span data-ttu-id="30751-112">기본 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-112">Add the default constructors:</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }
    }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub
    End Class
    ```

1. <span data-ttu-id="30751-113">추가 속성 및 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-113">Define any additional properties and constructors:</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public string StudentName { get; }

        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }

        public StudentNotFoundException(string message, string studentName)
            : this(message)
        {
            StudentName = studentName;
        }
    }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public ReadOnly Property StudentName As String

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub

        Public Sub New(message As String, studentName As String)
            Me.New(message)
            StudentName = studentName
        End Sub
    End Class
    ```

## <a name="create-localized-exception-messages"></a><span data-ttu-id="30751-114">지역화된 예외 메시지 만들기</span><span class="sxs-lookup"><span data-stu-id="30751-114">Create localized exception messages</span></span>

<span data-ttu-id="30751-115">사용자 지정 예외를 만들고 다음과 같은 코드를 사용하여 어디에서든 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30751-115">You have created a custom exception, and you can throw it anywhere with code like the following:</span></span>

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

```vb
Throw New StudentNotFoundException("The student cannot be found.", "John")
```

<span data-ttu-id="30751-116">이전 줄의 문제는 `"The student cannot be found."`이 상수 문자열에 불과하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30751-116">The problem with the previous line is that `"The student cannot be found."` is just a constant string.</span></span> <span data-ttu-id="30751-117">지역화된 애플리케이션에서는 사용자 문화권에 따라 다른 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30751-117">In a localized application, you want to have different messages depending on user culture.</span></span>
<span data-ttu-id="30751-118">[위성 어셈블리](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)는 이 작업을 수행하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="30751-118">[Satellite Assemblies](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) are a good way to do that.</span></span> <span data-ttu-id="30751-119">위성 어셈블리는 특정 언어에 대한 리소스를 포함하는 .dll입니다.</span><span class="sxs-lookup"><span data-stu-id="30751-119">A satellite assembly is a .dll that contains resources for a specific language.</span></span> <span data-ttu-id="30751-120">런타임에 특정 리소스를 요청하면 CLR은 사용자 문화권에 따라 해당 리소스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="30751-120">When you ask for a specific resources at run time, the CLR finds that resource depending on user culture.</span></span> <span data-ttu-id="30751-121">해당 문화권에 대한 위성 어셈블리를 찾을 수 없는 경우에는 기본 문화권의 리소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30751-121">If no satellite assembly is found for that culture, the resources of the default culture are used.</span></span>

<span data-ttu-id="30751-122">지역화된 예외 메시지를 만들려면</span><span class="sxs-lookup"><span data-stu-id="30751-122">To create the localized exception messages:</span></span>

1. <span data-ttu-id="30751-123">리소스 파일을 저장한 *Resources*라는 새 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30751-123">Create a new folder named *Resources* to hold the resource files.</span></span>
1. <span data-ttu-id="30751-124">새 리소스 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-124">Add a new resource file to it.</span></span> <span data-ttu-id="30751-125">Visual Studio에서 이렇게 하려면 **솔루션 탐색기**에서 폴더를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목** > **리소스 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-125">To do that in Visual Studio, right-click the folder in **Solution Explorer**, and select **Add** > **New Item** > **Resources File**.</span></span> <span data-ttu-id="30751-126">파일 이름을 *ExceptionMessages.resx*입니다.</span><span class="sxs-lookup"><span data-stu-id="30751-126">Name the file *ExceptionMessages.resx*.</span></span> <span data-ttu-id="30751-127">이 파일은 기본 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="30751-127">This is the default resources file.</span></span>
1. <span data-ttu-id="30751-128">다음 그림에 표시된 것처럼 예외 메시지에 대한 이름/값 쌍을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-128">Add a name/value pair for your exception message, like the following image shows:</span></span>

   ![기본 문화권에 리소스 추가](media/add-resources-to-default-culture.jpg)

1. <span data-ttu-id="30751-130">프랑스어의 새 리소스 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-130">Add a new resource file for French.</span></span> <span data-ttu-id="30751-131">이름을 *ExceptionMessages.fr-FR.resx*로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-131">Name it *ExceptionMessages.fr-FR.resx*.</span></span>
1. <span data-ttu-id="30751-132">예외 메시지에 대한 이름/값 쌍을 다시 추가하지만 이번에는 다음과 같은 프랑스 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-132">Add a name/value pair for the exception message again, but with a French value:</span></span>

   ![fr-FR 문화권에 리소스 추가](media/add-resources-to-fr-culture.jpg)

1. <span data-ttu-id="30751-134">프로젝트를 빌드하면 빌드 출력 폴더에는 위성 어셈블리인 *.dll* 파일을 포함하는 *fr-FR* 폴더가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-134">After you build the project, the build output folder should contain the *fr-FR* folder with a *.dll* file, which is the satellite assembly.</span></span>
1. <span data-ttu-id="30751-135">다음과 같은 코드를 사용하여 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="30751-135">You throw the exception with code like the following:</span></span>

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

    ```vb
    Dim resourceManager As New ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly())
    Throw New StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John")
    ```

    > [!NOTE]
    > <span data-ttu-id="30751-136">프로젝트 이름이 `TestProject`이고 리소스 파일 *ExceptionMessages.resx*가 프로젝트의 *Resources* 폴더에 있는 경우 리소스 파일의 정규화된 이름은 `TestProject.Resources.ExceptionMessages`입니다.</span><span class="sxs-lookup"><span data-stu-id="30751-136">If the project name is `TestProject` and the resource file *ExceptionMessages.resx* resides in the *Resources* folder of the project, the fully qualified name of the resource file is `TestProject.Resources.ExceptionMessages`.</span></span>

## <a name="see-also"></a><span data-ttu-id="30751-137">참조</span><span class="sxs-lookup"><span data-stu-id="30751-137">See also</span></span>

- [<span data-ttu-id="30751-138">사용자 정의 예외를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="30751-138">How to create user-defined exceptions</span></span>](how-to-create-user-defined-exceptions.md)
- [<span data-ttu-id="30751-139">데스크톱 응용 프로그램용 위성 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="30751-139">Creating Satellite Assemblies for Desktop Apps</span></span>](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [<span data-ttu-id="30751-140">base(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="30751-140">base (C# Reference)</span></span>](../../csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="30751-141">this(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="30751-141">this (C# Reference)</span></span>](../../csharp/language-reference/keywords/this.md)
