---
title: 양식 및 유효성 검사
description: 에서 클라이언트 쪽 유효성 검사를 사용 하 여 폼을 빌드하는 방법을 알아봅니다 Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: d2dce23996e996a736b04c9cdd1ccf3b549ff3ff
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267557"
---
# <a name="forms-and-validation"></a><span data-ttu-id="f0473-103">양식 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f0473-103">Forms and validation</span></span>

<span data-ttu-id="f0473-104">ASP.NET Web Forms 프레임 워크에는 폼 ( `RequiredFieldValidator` ,, `CompareValidator` 등)에 입력 된 사용자 입력의 유효성 검사를 처리 하는 유효성 검사 서버 컨트롤 집합이 포함 되어 있습니다 `RangeValidator` .</span><span class="sxs-lookup"><span data-stu-id="f0473-104">The ASP.NET Web Forms framework includes a set of validation server controls that handle validating user input entered into a form (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`, and so on).</span></span> <span data-ttu-id="f0473-105">ASP.NET Web Forms 프레임 워크는 또한 모델 바인딩과 데이터 주석 (,, 등)을 기반으로 모델의 유효성 검사를 지원 `[Required]` `[StringLength]` `[Range]` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-105">The ASP.NET Web Forms framework also supports model binding and validating the model based on data annotations (`[Required]`, `[StringLength]`, `[Range]`, and so on).</span></span> <span data-ttu-id="f0473-106">유효성 검사 논리는 서버와 클라이언트에서 모두 비 JavaScript 기반 유효성 검사를 사용 하 여 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-106">The validation logic can be enforced both on the server and on the client using unobtrusive JavaScript-based validation.</span></span> <span data-ttu-id="f0473-107">`ValidationSummary`서버 컨트롤은 유효성 검사 오류에 대 한 요약을 사용자에 게 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-107">The `ValidationSummary` server control is used to display a summary of the validation errors to the user.</span></span>

<span data-ttu-id="f0473-108">Blazor 는 클라이언트와 서버 둘 다에서 유효성 검사 논리를 공유할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-108">Blazor supports the sharing of validation logic between both the client and the server.</span></span> <span data-ttu-id="f0473-109">ASP.NET는 많은 일반 서버 유효성 검사에 대 한 미리 빌드된 JavaScript 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-109">ASP.NET provides pre-built JavaScript implementations of many common server validations.</span></span> <span data-ttu-id="f0473-110">대부분의 경우 개발자는 응용 프로그램별 유효성 검사 논리를 완전히 구현 하기 위해 JavaScript를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-110">In many cases, the developer still has to write JavaScript to fully implement their app-specific validation logic.</span></span> <span data-ttu-id="f0473-111">서버와 클라이언트 모두에서 동일한 모델 유형, 데이터 주석 및 유효성 검사 논리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-111">The same model types, data annotations, and validation logic can be used on both the server and client.</span></span>

<span data-ttu-id="f0473-112">Blazor 입력 구성 요소 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-112">Blazor provides a set of input components.</span></span> <span data-ttu-id="f0473-113">입력 구성 요소는 필드 데이터를 모델에 바인딩하고 폼이 제출 될 때 사용자 입력의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-113">The input components handle binding field data to a model and validating the user input when the form is submitted.</span></span>

|<span data-ttu-id="f0473-114">입력 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f0473-114">Input component</span></span>|<span data-ttu-id="f0473-115">렌더링 된 HTML 요소</span><span class="sxs-lookup"><span data-stu-id="f0473-115">Rendered HTML element</span></span>    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

<span data-ttu-id="f0473-116">`EditForm`구성 요소는 이러한 입력 구성 요소를 래핑하고를 통해 유효성 검사 프로세스를 오케스트레이션 합니다 `EditContext` .</span><span class="sxs-lookup"><span data-stu-id="f0473-116">The `EditForm` component wraps these input components and orchestrates the validation process through an `EditContext`.</span></span> <span data-ttu-id="f0473-117">를 만들 때 `EditForm` 매개 변수를 사용 하 여 바인딩할 모델 인스턴스를 지정 `Model` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-117">When creating an `EditForm`, you specify what model instance to bind to using the `Model` parameter.</span></span> <span data-ttu-id="f0473-118">유효성 검사는 일반적으로 데이터 주석을 사용 하 여 수행 되며 확장 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-118">Validation is typically done using data annotations, and it's extensible.</span></span> <span data-ttu-id="f0473-119">데이터 주석 기반 유효성 검사를 사용 하도록 설정 하려면 `DataAnnotationsValidator` 구성 요소를의 자식으로 추가 `EditForm` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-119">To enable data annotation-based validation, add the `DataAnnotationsValidator` component as a child of the `EditForm`.</span></span> <span data-ttu-id="f0473-120">`EditForm`구성 요소는 유효한 ( `OnValidSubmit` ) 및 잘못 된 () 제출을 처리 하는 편리한 이벤트를 제공 합니다 `OnInvalidSubmit` .</span><span class="sxs-lookup"><span data-stu-id="f0473-120">The `EditForm` component provides a convenient event for handling valid (`OnValidSubmit`) and invalid (`OnInvalidSubmit`) submissions.</span></span> <span data-ttu-id="f0473-121">또한 `OnSubmit` 직접 유효성 검사를 트리거하고 처리할 수 있는 더 많은 일반 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-121">There's also a more generic `OnSubmit` event that lets you trigger and handle the validation yourself.</span></span>

<span data-ttu-id="f0473-122">유효성 검사 오류 요약을 표시 하려면 `ValidationSummary` 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-122">To display a validation error summary, use the `ValidationSummary` component.</span></span> <span data-ttu-id="f0473-123">특정 입력 필드에 대 한 유효성 검사 메시지를 표시 하려면 구성 요소를 사용 하 여 `ValidationMessage` 적절 한 `For` 모델 멤버를 가리키는 매개 변수에 대 한 람다 식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-123">To display validation messages for a specific input field, use the `ValidationMessage` component, specifying a lambda expression for the `For` parameter that points to the appropriate model member.</span></span>

<span data-ttu-id="f0473-124">다음 모델 유형은 데이터 주석을 사용 하 여 여러 유효성 검사 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-124">The following model type defines several validation rules using data annotations:</span></span>

```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Starship
{
    [Required]
    [StringLength(16,
        ErrorMessage = "Identifier too long (16 character limit).")]
    public string Identifier { get; set; }

    public string Description { get; set; }

    [Required]
    public string Classification { get; set; }

    [Range(1, 100000,
        ErrorMessage = "Accommodation invalid (1-100000).")]
    public int MaximumAccommodation { get; set; }

    [Required]
    [Range(typeof(bool), "true", "true",
        ErrorMessage = "This form disallows unapproved ships.")]
    public bool IsValidatedDesign { get; set; }

    [Required]
    public DateTime ProductionDate { get; set; }
}
```

<span data-ttu-id="f0473-125">다음 구성 요소는 Blazor 모델 유형을 기반으로에서 양식을 작성 하는 방법을 보여 줍니다 `Starship` .</span><span class="sxs-lookup"><span data-stu-id="f0473-125">The following component demonstrates building a form in Blazor based on the `Starship` model type:</span></span>

```razor
<h1>New Ship Entry Form</h1>

<EditForm Model="@starship" OnValidSubmit="@HandleValidSubmit">
    <DataAnnotationsValidator />
    <ValidationSummary />

    <p>
        <label for="identifier">Identifier: </label>
        <InputText id="identifier" @bind-Value="starship.Identifier" />
        <ValidationMessage For="() => starship.Identifier" />
    </p>
    <p>
        <label for="description">Description (optional): </label>
        <InputTextArea id="description" @bind-Value="starship.Description" />
    </p>
    <p>
        <label for="classification">Primary Classification: </label>
        <InputSelect id="classification" @bind-Value="starship.Classification">
            <option value="">Select classification ...</option>
            <option value="Exploration">Exploration</option>
            <option value="Diplomacy">Diplomacy</option>
            <option value="Defense">Defense</option>
        </InputSelect>
        <ValidationMessage For="() => starship.Classification" />
    </p>
    <p>
        <label for="accommodation">Maximum Accommodation: </label>
        <InputNumber id="accommodation" @bind-Value="starship.MaximumAccommodation" />
        <ValidationMessage For="() => starship.MaximumAccommodation" />
    </p>
    <p>
        <label for="valid">Engineering Approval: </label>
        <InputCheckbox id="valid" @bind-Value="starship.IsValidatedDesign" />
        <ValidationMessage For="() => starship.IsValidatedDesign" />
    </p>
    <p>
        <label for="productionDate">Production Date: </label>
        <InputDate id="productionDate" @bind-Value="starship.ProductionDate" />
        <ValidationMessage For="() => starship.ProductionDate" />
    </p>

    <button type="submit">Submit</button>
</EditForm>

@code {
    private Starship starship = new Starship();

    private void HandleValidSubmit()
    {
        // Save the data
    }
}
```

<span data-ttu-id="f0473-126">양식 전송 후 모델 바인딩 데이터는 데이터베이스와 같은 모든 데이터 저장소에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-126">After the form submission, the model-bound data hasn't been saved to any data store, like a database.</span></span> <span data-ttu-id="f0473-127">앱에서 Blazor WebAssembly 데이터를 서버로 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-127">In a Blazor WebAssembly app, the data must be sent to the server.</span></span> <span data-ttu-id="f0473-128">예를 들어 HTTP POST 요청을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-128">For example, using an HTTP POST request.</span></span> <span data-ttu-id="f0473-129">Blazor서버 앱에서 데이터는 이미 서버에 있지만 지속 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-129">In a Blazor Server app, the data is already on the server, but it must be persisted.</span></span> <span data-ttu-id="f0473-130">응용 프로그램에서 데이터 액세스를 처리 하는 Blazor 것은 [데이터](data.md) 처리 섹션의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="f0473-130">Handling data access in Blazor apps is the subject of the [Dealing with data](data.md) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0473-131">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="f0473-131">Additional resources</span></span>

<span data-ttu-id="f0473-132">앱의 [폼 및 유효성 검사](/aspnet/core/blazor/forms-validation) 에 대 한 자세한 내용은 Blazor 설명서를 참조 Blazor 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0473-132">For more information on [forms and validation](/aspnet/core/blazor/forms-validation) in Blazor apps, see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f0473-133">[이전](state-management.md)
>[다음](data.md)</span><span class="sxs-lookup"><span data-stu-id="f0473-133">[Previous](state-management.md)
[Next](data.md)</span></span>
