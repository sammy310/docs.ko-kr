---
title: Error 문
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 668ffbc7b8db73a706c5771bb0734a77f8fc0206
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351246"
---
# <a name="error-statement"></a><span data-ttu-id="64968-102">Error 문</span><span class="sxs-lookup"><span data-stu-id="64968-102">Error Statement</span></span>
<span data-ttu-id="64968-103">오류가 발생 한 경우를 시뮬레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="64968-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64968-104">구문</span><span class="sxs-lookup"><span data-stu-id="64968-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="64968-105">요소</span><span class="sxs-lookup"><span data-stu-id="64968-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="64968-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="64968-106">Required.</span></span> <span data-ttu-id="64968-107">모든 유효한 오류 번호가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64968-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64968-108">주의</span><span class="sxs-lookup"><span data-stu-id="64968-108">Remarks</span></span>  
 <span data-ttu-id="64968-109">`Error` 문은 이전 버전과의 호환성을 위해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64968-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="64968-110">새 코드에서 특히 개체를 만들 때 `Err` 개체의 `Raise` 메서드를 사용 하 여 런타임 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64968-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="64968-111">`errornumber` 정의 된 경우 `Error` 문은 `Err` 개체의 속성에 다음과 같은 기본값을 할당 한 후에 오류 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="64968-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="64968-112">속성</span><span class="sxs-lookup"><span data-stu-id="64968-112">Property</span></span>|<span data-ttu-id="64968-113">값</span><span class="sxs-lookup"><span data-stu-id="64968-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="64968-114">`Error` 문에 대 한 인수로 지정 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="64968-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="64968-115">모든 유효한 오류 번호가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64968-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="64968-116">현재 Visual Basic 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="64968-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="64968-117">지정 된 `Number`에 대 한 `Error` 함수의 반환 값에 해당 하는 문자열 식입니다 (이 문자열이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="64968-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="64968-118">문자열이 없으면 `Description`에 길이가 0 인 문자열 ("")이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64968-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="64968-119">적절 한 Visual Basic 도움말 파일의 정규화 된 드라이브, 경로 및 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="64968-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="64968-120">`Number` 속성에 해당 하는 오류에 대 한 적절 한 Visual Basic 도움말 파일 컨텍스트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="64968-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="64968-121">0입니다.</span><span class="sxs-lookup"><span data-stu-id="64968-121">Zero.</span></span>|  
  
 <span data-ttu-id="64968-122">오류 처리기가 없거나 사용할 수 없는 경우에는 오류 메시지가 생성 되 고 `Err` 개체 속성에서 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64968-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64968-123">일부 Visual Basic 호스트 응용 프로그램에서 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64968-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="64968-124">클래스 및 개체를 만들 수 있는지 여부를 확인 하려면 호스트 응용 프로그램의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64968-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64968-125">예제</span><span class="sxs-lookup"><span data-stu-id="64968-125">Example</span></span>  
 <span data-ttu-id="64968-126">이 예에서는 `Error` 문을 사용 하 여 오류 번호 11을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64968-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="64968-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64968-127">Requirements</span></span>  
 <span data-ttu-id="64968-128">**네임 스페이스:** [microsoft.visualbasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="64968-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="64968-129">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.visualbasic)</span><span class="sxs-lookup"><span data-stu-id="64968-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64968-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64968-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="64968-131">On Error 문</span><span class="sxs-lookup"><span data-stu-id="64968-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="64968-132">Resume 문</span><span class="sxs-lookup"><span data-stu-id="64968-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="64968-133">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="64968-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
