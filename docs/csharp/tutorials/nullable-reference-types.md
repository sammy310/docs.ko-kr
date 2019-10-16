---
title: nullable 참조 형식을 사용하여 디자인
description: 이 고급 자습서에서는 nullable 참조 형식을 소개합니다. 참조 값이 null일 수 있는 경우에 대한 디자인 의도를 표현하고 컴파일러가 null일 수 없는 경우를 적용하게 하는 방법을 알아봅니다.
ms.date: 02/19/2019
ms.custom: mvc
ms.openlocfilehash: e58f2bac23fabf734df93aa2a643106f1c1bd5f3
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291381"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="2f429-104">자습서: nullable 참조 형식 및 nullable이 아닌 참조 형식을 사용하여 디자인 의도를 보다 명확하게 표현</span><span class="sxs-lookup"><span data-stu-id="2f429-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="2f429-105">C# 8.0에서는 nullable 값 형식이 값 형식을 보완하는 것과 동일한 방식으로 참조 형식을 보완하는 [nullable 참조 형식](../nullable-references.md)이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-105">C# 8.0 introduces [nullable reference types](../nullable-references.md), which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="2f429-106">형식에 `?`를 추가하여 변수를 **nullable 참조 형식**으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="2f429-107">예를 들어 `string?`는 nullable `string`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="2f429-108">이러한 새 형식을 사용하여 디자인 의도를 보다 명확하게 표현할 수 있습니다. ‘항상 값이 있어야 하는’ 변수도 있고, ‘값이 누락될 수 있는’ 변수도 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="2f429-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="2f429-109">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="2f429-110">디자인에 nullable 참조 형식 및 nullable이 아닌 참조 형식 통합</span><span class="sxs-lookup"><span data-stu-id="2f429-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> - <span data-ttu-id="2f429-111">코드 전체에서 nullable 참조 형식 확인을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-111">Enable nullable reference type checks throughout your code.</span></span>
> - <span data-ttu-id="2f429-112">컴파일러가 이러한 디자인 결정을 적용하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-112">Write code where the compiler enforces those design decisions.</span></span>
> - <span data-ttu-id="2f429-113">고유한 디자인에 nullable 참조 기능 사용</span><span class="sxs-lookup"><span data-stu-id="2f429-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f429-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="2f429-114">Prerequisites</span></span>

<span data-ttu-id="2f429-115">C# 8.0 컴파일러를 포함하여 .NET Core를 실행하도록 컴퓨터를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-115">You'll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="2f429-116">C# 8.0 컴파일러는 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 또는 [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-116">The C# 8.0 compiler is available with [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="2f429-117">이 자습서에서는 Visual Studio 또는 .NET Core CLI를 포함하여 C# 및 .NET에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="2f429-118">디자인에 nullable 참조 형식 통합</span><span class="sxs-lookup"><span data-stu-id="2f429-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="2f429-119">이 자습서에서는 설문 조사 실행을 모델링하는 라이브러리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="2f429-120">코드는 nullable 참조 형식 및 nullable이 아닌 참조 형식을 둘 다 사용하여 실제 세계의 개념을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="2f429-121">설문 조사 질문은 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-121">The survey questions can never be null.</span></span> <span data-ttu-id="2f429-122">응답자는 질문에 응답하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="2f429-123">이 경우 응답이 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-123">The responses might be `null` in this case.</span></span>

<span data-ttu-id="2f429-124">이 샘플에 대해 작성하는 코드는 해당 의도를 표현하고 컴파일러가 의도를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="2f429-125">애플리케이션을 만들고 nullable 참조 형식을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="2f429-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="2f429-126">Visual Studio 또는 `dotnet new console`을 사용하여 명령줄에서 새로운 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="2f429-127">애플리케이션 이름을 `NullableIntroduction`으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="2f429-128">애플리케이션을 만든 후에는 전체 프로젝트가 **활성화된 nullable 주석 컨텍스트**에서 컴파일하도록 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-128">Once you've created the application, you'll need to specify that the entire project compiles in an enabled **nullable annotation context**.</span></span> <span data-ttu-id="2f429-129">*.csproj* 파일을 열고 `Nullable` 요소에 `PropertyGroup` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-129">Open the *.csproj* file and add a `Nullable` element to the `PropertyGroup` element.</span></span> <span data-ttu-id="2f429-130">해당 값을 `enable`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-130">Set its value to `enable`.</span></span> <span data-ttu-id="2f429-131">C# 8.0 프로젝트에서도 **nullable 참조 형식** 기능을 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-131">You must opt into the **nullable reference types** feature, even in C# 8.0 projects.</span></span> <span data-ttu-id="2f429-132">기능이 켜지고 나면 기존 참조 변수 선언이 **nullable이 아닌 참조 형식**으로 바뀌기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-132">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="2f429-133">이러한 의사 결정은 기존 코드에 적절한 null 확인이 없다는 문제를 찾는 데는 도움이 되지만, 원래 설계 의도를 정확하게 반영하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-133">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent:</span></span>

```xml
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="2f429-134">애플리케이션의 형식 디자인</span><span class="sxs-lookup"><span data-stu-id="2f429-134">Design the types for the application</span></span>

<span data-ttu-id="2f429-135">이 설문 조사 애플리케이션에서는 다음과 같은 많은 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-135">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="2f429-136">질문 목록을 모델링하는 클래스</span><span class="sxs-lookup"><span data-stu-id="2f429-136">A class that models the list of questions.</span></span>
- <span data-ttu-id="2f429-137">설문 조사를 위해 연락한 사람 목록을 모델링하는 클래스</span><span class="sxs-lookup"><span data-stu-id="2f429-137">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="2f429-138">설문 조사를 수행한 사람의 응답을 모델링하는 클래스</span><span class="sxs-lookup"><span data-stu-id="2f429-138">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="2f429-139">이러한 형식은 nullable 참조 형식 및 nullable이 아닌 참조 형식을 둘 다 사용하여 필수 멤버가 선택적 멤버를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-139">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="2f429-140">nullable 참조 형식은 해당 디자인 의도를 명확하게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-140">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="2f429-141">설문 조사의 일부인 질문은 null일 수 없습니다. 빈 질문을 하는 것은 타당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-141">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="2f429-142">응답자는 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-142">The respondents can never be null.</span></span> <span data-ttu-id="2f429-143">참여를 거부한 응답자를 포함하여 연락한 사람을 추적하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-143">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="2f429-144">질문에 대한 응답은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-144">Any response to a question may be null.</span></span> <span data-ttu-id="2f429-145">응답자는 일부 또는 모든 질문에 대한 응답을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-145">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="2f429-146">C#으로 프로그래밍한 경우 `null` 값을 허용하는 참조 형식에 익숙해서 null 허용이 아닌 인스턴스를 선언할 다른 기회를 놓칠 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-146">If you've programmed in C#, you may be so accustomed to reference types that allow `null` values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="2f429-147">질문 컬렉션은 nullable이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-147">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="2f429-148">응답자 컬렉션은 nullable이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-148">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="2f429-149">코드를 작성할 때 null 허용이 아닌 참조 형식을 참조의 기본값으로 사용하면 <xref:System.NullReferenceException>을 발생시킬 수 있는 일반적인 실수를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-149">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to <xref:System.NullReferenceException>s.</span></span> <span data-ttu-id="2f429-150">이 자습서에서 배운 한 가지 교훈은 `null`일 수 있는 변수와 그렇지 않은 변수를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-150">One lesson from this tutorial is that you made decisions about which variables could or could not be `null`.</span></span> <span data-ttu-id="2f429-151">이러한 결정을 표현하는 구문은 언어에서 제공하지 않았지만</span><span class="sxs-lookup"><span data-stu-id="2f429-151">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="2f429-152">이제 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-152">Now it does.</span></span>

<span data-ttu-id="2f429-153">빌드할 앱은 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-153">The app you'll build does the following steps:</span></span>

1. <span data-ttu-id="2f429-154">설문 조사를 만들고 질문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-154">Creates a survey and adds questions to it.</span></span>
1. <span data-ttu-id="2f429-155">설문 조사 응답자의 의사 임의 세트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-155">Creates a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="2f429-156">완료된 설문 조사 크기가 목표 수치에 도달할 때까지 응답자에게 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-156">Contacts respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="2f429-157">설문 조사 응답에 대한 중요한 통계를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-157">Writes out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="2f429-158">nullable 형식과 nullable이 아닌 형식을 사용하여 설문 조사 작성</span><span class="sxs-lookup"><span data-stu-id="2f429-158">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="2f429-159">작성하는 첫 번째 코드에서 설문 조사를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-159">The first code you'll write creates the survey.</span></span> <span data-ttu-id="2f429-160">설문 조사 질문과 설문 조사 실행을 모델링하는 클래스를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-160">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="2f429-161">설문 조사에는 다음 응답 형식으로 구분되는 세 가지 질문 유형이 있습니다. 예/아니요 응답, 숫자 응답, 텍스트 응답.</span><span class="sxs-lookup"><span data-stu-id="2f429-161">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="2f429-162">`public SurveyQuestion` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-162">Create a `public SurveyQuestion` class:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="2f429-163">컴파일러가 모든 참조 형식 변수 선언을 활성화된 nullable 주석 컨텍스트에 있는 코드의 **nullable이 아닌** 참조 형식으로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-163">The compiler interprets every reference type variable declaration as a **non-nullable** reference type for code in an enabled nullable annotation context.</span></span> <span data-ttu-id="2f429-164">다음 코드에 표시된 대로 질문 텍스트 및 질문 유형의 속성을 추가하여 첫 번째 경고를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-164">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

<span data-ttu-id="2f429-165">`QuestionText`를 초기화하지 않았기 때문에 컴파일러에서 nullable이 아닌 속성이 초기화되지 않았다는 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-165">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="2f429-166">디자인에 따라 질문 텍스트는 null이 아니어야 하므로 초기화할 생성자와 `QuestionType` 값도 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-166">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="2f429-167">완성된 클래스 정의는 다음 코드와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-167">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="2f429-168">생성자를 추가하면 경고가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-168">Adding the constructor removes the warning.</span></span> <span data-ttu-id="2f429-169">생성자 인수도 nullable이 아닌 참조 형식이므로 컴파일러에서 경고를 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-169">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="2f429-170">`SurveyRun`이라는 `public` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-170">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="2f429-171">이 클래스에는 다음 코드에 표시된 것처럼 설문 조사에 질문을 추가하는 메서드 및 `SurveyQuestion` 개체 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-171">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

<span data-ttu-id="2f429-172">이전과 마찬가지로, 목록 개체를 null이 아닌 값으로 초기화해야 합니다. 초기화하지 않으면 컴파일러에서 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-172">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="2f429-173">`AddQuestion`의 두 번째 오버로드에는 null 확인이 없습니다. 왜냐하면 해당 변수를 nullable이 아닌 것으로 선언했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-173">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="2f429-174">해당 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-174">Its value can't be `null`.</span></span>

<span data-ttu-id="2f429-175">편집기에서 *Program.cs*로 전환하고 `Main`의 내용을 다음 코드 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-175">Switch to *Program.cs* in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](~/samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="2f429-176">프로젝트 전체가 활성화된 nullable 주석 컨텍스트이므로 nullable이 아닌 참조 형식을 기대하고 메서드로 `null`을 전달하면 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-176">Because the entire project is in an enabled nullable annotation context, you'll get warnings when you pass `null` to any method expecting a non-nullable reference type.</span></span> <span data-ttu-id="2f429-177">다음 줄을 `Main`에 추가하여 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2f429-177">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="2f429-178">응답자를 만들고 설문 조사에 대한 응답 받기</span><span class="sxs-lookup"><span data-stu-id="2f429-178">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="2f429-179">다음으로, 설문 조사에 대한 응답을 생성하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-179">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="2f429-180">이 프로세스에는 몇 개의 작은 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-180">This process involves several small tasks:</span></span>

1. <span data-ttu-id="2f429-181">응답자 개체를 생성하는 메서드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-181">Build a method that generates respondent objects.</span></span> <span data-ttu-id="2f429-182">이러한 개체는 설문 조사를 작성하도록 요청된 사람을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-182">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="2f429-183">응답자에게 질문하고 응답을 수집하거나 응답자가 응답하지 않았음을 확인하는 과정을 시뮬레이션하는 논리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-183">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="2f429-184">충분한 응답자가 설문 조사에 응답할 때까지 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-184">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="2f429-185">설문 조사 응답을 나타낼 클래스가 필요하므로 지금 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-185">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="2f429-186">nullable 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-186">Enable nullable support.</span></span> <span data-ttu-id="2f429-187">다음 코드에 표시된 대로 `Id` 속성 및 이 속성을 초기화하는 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-187">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="2f429-188">다음으로, `static` 메서드를 추가해서 임의 ID를 생성하여 새 참가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-188">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="2f429-189">이 클래스의 주요 책임은 설문 조사의 질문에 대한 참가자의 응답을 생성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-189">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="2f429-190">이 책임에는 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-190">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="2f429-191">설문 조사에 참여하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-191">Ask for participation in the survey.</span></span> <span data-ttu-id="2f429-192">개인이 동의하지 않을 경우 missing(또는 null) 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-192">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="2f429-193">각 질문을 하고 응답을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-193">Ask each question and record the answer.</span></span> <span data-ttu-id="2f429-194">각 응답도 missing(또는 null)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-194">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="2f429-195">`SurveyResponse` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-195">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="2f429-196">설문 조사 응답의 스토리지는 `Dictionary<int, string>?`로, null일 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-196">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="2f429-197">새 언어 기능을 사용하여 컴파일러 및 나중에 코드를 읽는 모든 사람에게 디자인 의도를 선언하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-197">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="2f429-198">먼저 `null` 값을 확인하지 않고 `surveyResponses`를 역참조하는 경우 컴파일러 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-198">If you ever dereference `surveyResponses` without checking for the `null` value first, you'll get a compiler warning.</span></span> <span data-ttu-id="2f429-199">위에서 `surveyResponses` 변수가 null이 아닌 값으로 설정되었음을 컴파일러가 판별할 수 있으므로 `AnswerSurvey` 메서드에 경고가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-199">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="2f429-200">누락된 응답을 확인하기 위해 `null`을 사용하는 것에서 nullable 참조 형식을 사용할 때 유의해야 할 중요한 점을 확인할 수 있습니다. 즉, 프로그램에서 `null` 값을 모두 제거하는 것이 목표가 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-200">Using `null` for missing answers highlights a key point for working with nullable reference types: your goal isn't to remove all `null` values from your program.</span></span> <span data-ttu-id="2f429-201">내가 작성하는 코드가 내 설계 의도를 그대로 표현하고 있는지 확인하는 것이 목표가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-201">Rather, your goal is to ensure that the code you write expresses the intent of your design.</span></span> <span data-ttu-id="2f429-202">누락된 값은 코드에서 반드시 표현해야 하는 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-202">Missing values are a necessary concept to express in your code.</span></span> <span data-ttu-id="2f429-203">`null` 값은 누락된 값을 분명하게 표현할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-203">The `null` value is a clear way to express those missing values.</span></span> <span data-ttu-id="2f429-204">`null` 값을 모두 제거하는 것을 목표로 하면 `null`을 사용하지 않고 누락된 값을 표현할 다른 방법을 정의해야 할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-204">Trying to remove all `null` values only leads to defining some other way to express those missing values without `null`.</span></span>

<span data-ttu-id="2f429-205">다음으로, `SurveyRun` 클래스에 `PerformSurvey` 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-205">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="2f429-206">`SurveyRun` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-206">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="2f429-207">여기서 다시, nullable `List<SurveyResponse>?` 선택은 응답이 null일 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-207">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="2f429-208">이는 설문 조사가 아직 어떠한 응답자에게도 제공되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-208">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="2f429-209">충분한 응답자가 동의할 때까지 응답자가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-209">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="2f429-210">설문 조사를 실행하는 마지막 단계는 `Main` 메서드의 끝에 설문 조사를 수행할 호출을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-210">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](~/samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="2f429-211">설문 조사 응답 조사</span><span class="sxs-lookup"><span data-stu-id="2f429-211">Examine survey responses</span></span>

<span data-ttu-id="2f429-212">마지막 단계는 설문 조사 결과를 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-212">The last step is to display survey results.</span></span> <span data-ttu-id="2f429-213">작성한 여러 클래스에 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-213">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="2f429-214">이 코드는 nullable 참조 형식과 nullable이 아닌 참조 형식 구분의 가치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-214">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="2f429-215">먼저 다음 두 개의 식 본문 멤버를 `SurveyResponse` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-215">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="2f429-216">`surveyResponses`는 null이 가능한 참조 형식이므로 역참조하기 전에 null 확인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-216">Because `surveyResponses` is a nullable reference type, null checks are necessary before de-referencing it.</span></span> <span data-ttu-id="2f429-217">`Answer` 메서드는 null 허용이 아닌 문자열을 반환하므로 null 병합 연산자를 사용하여 누락된 답변의 사례를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-217">The `Answer` method returns a non-nullable string, so we have to cover the case of a missing answer by using the null-coalescing operator.</span></span>

<span data-ttu-id="2f429-218">다음 세 개의 식 본문 멤버를 `SurveyRun` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-218">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="2f429-219">`respondents` 변수는 null일 수 있지만 반환 값은 null일 수 없음을 `AllParticipants` 멤버가 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-219">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="2f429-220">`??` 및 뒤에 오는 빈 시퀀스를 제거하여 해당 식을 변경하면 컴파일러에서 메서드가 `null`을 반환할 수 있고 해당 반환 시그니처가 nullable이 아닌 형식을 반환한다고 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-220">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="2f429-221">마지막으로, `Main` 메서드의 맨 아래에 다음 루프를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-221">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](~/samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="2f429-222">모두 nullable이 아닌 참조 형식을 반환하도록 기본 인터페이스를 디자인했기 때문에 이 코드에는 `null` 확인이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-222">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="2f429-223">코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="2f429-223">Get the code</span></span>

<span data-ttu-id="2f429-224">[csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) 폴더의 [samples](https://github.com/dotnet/samples) 리포지토리에서 완료된 자습서의 코드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-224">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="2f429-225">nullable 참조 형식과 nullable이 아닌 참조 형식 간에 형식 선언을 변경하여 실험합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-225">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="2f429-226">실수로 `null`을 역참조하지 않도록 어떻게 다양한 경고를 생성하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f429-226">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2f429-227">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2f429-227">Next steps</span></span>

<span data-ttu-id="2f429-228">nullable 참조 형식을 사용할 수 있도록 기존 애플리케이션을 마이그레이션하여 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2f429-228">Learn more by migrating an existing application to use nullable reference types:</span></span>
> [!div class="nextstepaction"]
> <span data-ttu-id="2f429-229">[Upgrade an application to use nullable reference types](upgrade-to-nullable-references.md)(nullable 참조 형식을 사용할 수 있도록 애플리케이션 업그레이드)</span><span class="sxs-lookup"><span data-stu-id="2f429-229">[Upgrade an application to use nullable reference types](upgrade-to-nullable-references.md)</span></span>
