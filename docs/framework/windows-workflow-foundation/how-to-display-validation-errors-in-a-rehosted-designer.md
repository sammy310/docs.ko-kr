---
description: '자세히 알아보기: 방법: 재 호스트 된 디자이너에서 유효성 검사 오류 표시'
title: '방법: 다시 호스트된 디자이너에서 유효성 검사 오류 표시'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: 75ff45e6e9a81df96a9940ce21d1b160cab1000e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777738"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="c9593-103">방법: 다시 호스트된 디자이너에서 유효성 검사 오류 표시</span><span class="sxs-lookup"><span data-stu-id="c9593-103">How to: Display Validation Errors in a Rehosted Designer</span></span>

<span data-ttu-id="c9593-104">이 항목에서는 재 호스트 된 Windows 워크플로 디자이너에서 유효성 검사 오류를 검색 하 고 게시 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-104">This topic describes how to retrieve and publish validation errors in a rehosted Windows Workflow Designer.</span></span> <span data-ttu-id="c9593-105">또한 다시 호스트된 디자이너의 워크플로가 유효한지 확인하는 절차도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-105">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="c9593-106">이 작업은 두 부분으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-106">This task has two parts.</span></span> <span data-ttu-id="c9593-107">첫 번째 부분은 <xref:System.Activities.Presentation.Validation.IValidationErrorService> 구현을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-107">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="c9593-108">이 인터페이스에서 구현할 중요한 메서드인 <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>가 있습니다. 이 메서드는 디버그 로그 오류에 대한 정보가 들어 있는 <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> 개체 목록을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-108">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="c9593-109">인터페이스를 구현한 후 해당 구현의 인스턴스를 편집 컨텍스트에 게시하여 오류 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-109">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="c9593-110">IValidationErrorService 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="c9593-110">Implement the IValidationErrorService Interface</span></span>  
  
1. <span data-ttu-id="c9593-111">다음은 유효성 검사 오류를 디버그 로그에 쓰는 간단한 구현을 위한 코드 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-111">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
    ```csharp  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine($"Error: {vei.Message}"));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="c9593-112">편집 컨텍스트에 게시</span><span class="sxs-lookup"><span data-stu-id="c9593-112">Publishing to the Editing Context</span></span>  
  
1. <span data-ttu-id="c9593-113">다음은 이 인스턴스를 편집 컨텍스트에 게시하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c9593-113">Here is the code that will publish this to the editing context.</span></span>  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
