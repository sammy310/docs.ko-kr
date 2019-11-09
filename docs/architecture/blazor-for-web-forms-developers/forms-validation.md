---
title: 양식 및 유효성 검사
description: Blazor에서 클라이언트 쪽 유효성 검사를 사용 하 여 폼을 빌드하는 방법을 알아봅니다.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: c30db5e06d36a6d15301835fe782b21058a80592
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841956"
---
# <a name="forms-and-validation"></a>양식 및 유효성 검사

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Web Forms 프레임 워크에는 폼에 입력 한 사용자 입력의 유효성 검사를 처리 하는 유효성 검사 서버 컨트롤 집합 (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`등)이 포함 되어 있습니다. ASP.NET Web Forms 프레임 워크는 또한 모델 바인딩과 데이터 주석 (`[Required]`, `[StringLength]`, `[Range]`등)을 기반으로 모델의 유효성 검사를 지원 합니다. 유효성 검사 논리는 서버와 클라이언트에서 모두 비 JavaScript 기반 유효성 검사를 사용 하 여 적용할 수 있습니다. `ValidationSummary` 서버 컨트롤은 유효성 검사 오류에 대 한 요약을 사용자에 게 표시 하는 데 사용 됩니다.

Blazor는 클라이언트와 서버 둘 다에서 유효성 검사 논리를 공유할 수 있도록 지원 합니다. ASP.NET는 많은 일반 서버 유효성 검사에 대 한 미리 빌드된 JavaScript 구현을 제공 합니다. 대부분의 경우 개발자는 응용 프로그램별 유효성 검사 논리를 완전히 구현 하기 위해 JavaScript를 작성 해야 합니다. 서버와 클라이언트 모두에서 동일한 모델 유형, 데이터 주석 및 유효성 검사 논리를 사용할 수 있습니다.

Blazor는 입력 구성 요소 집합을 제공 합니다. 입력 구성 요소는 필드 데이터를 모델에 바인딩하고 폼이 제출 될 때 사용자 입력의 유효성을 검사 합니다.

|입력 구성 요소|렌더링 된 HTML 요소    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

`EditForm` 구성 요소는 이러한 입력 구성 요소를 래핑하고 `EditContext`를 통해 유효성 검사 프로세스를 오케스트레이션 합니다. `EditForm`를 만들 때 `Model` 매개 변수를 사용 하 여 바인딩할 모델 인스턴스를 지정 합니다. 유효성 검사는 일반적으로 데이터 주석을 사용 하 여 수행 되며 확장 가능 합니다. 데이터 주석 기반 유효성 검사를 사용 하도록 설정 하려면 `DataAnnotationsValidator` 구성 요소를 `EditForm`의 자식으로 추가 합니다. `EditForm` 구성 요소는 유효한 (`OnValidSubmit`) 및 잘못 된 (`OnInvalidSubmit`) 제출을 처리 하는 편리한 이벤트를 제공 합니다. 또한 직접 유효성 검사를 트리거하고 처리할 수 있는 보다 일반적인 `OnSubmit` 이벤트가 있습니다.

유효성 검사 오류 요약을 표시 하려면 `ValidationSummary` 구성 요소를 사용 합니다. 특정 입력 필드에 대 한 유효성 검사 메시지를 표시 하려면 `ValidationMessage` 구성 요소를 사용 하 여 적절 한 모델 멤버를 가리키는 `For` 매개 변수에 대 한 람다 식을 지정 합니다.

다음 모델 유형은 데이터 주석을 사용 하 여 여러 유효성 검사 규칙을 정의 합니다.

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

다음 구성 요소는 `Starship` 모델 유형을 기반으로 Blazor에서 양식을 작성 하는 방법을 보여 줍니다.

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

양식 전송 후 모델 바인딩 데이터는 데이터베이스와 같은 모든 데이터 저장소에 저장 되지 않습니다. Blazor Weasembomapp에서 데이터는 서버로 전송 되어야 합니다. 예를 들어 HTTP POST 요청을 사용 합니다. Blazor 서버 앱에서 데이터는 이미 서버에 있지만 지속 되어야 합니다. Blazor apps에서 데이터 액세스를 처리 하는 것은 [데이터](data.md) 처리 섹션의 제목입니다.

## <a name="additional-resources"></a>추가 자료

Blazor apps의 [폼 및 유효성 검사](/aspnet/core/blazor/forms-validation) 에 대 한 자세한 내용은 Blazor 설명서를 참조 하세요.

>[!div class="step-by-step"]
>[이전](state-management.md)
>[다음](data.md)
