---
title: Error 문 (Visual Basic)
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
ms.openlocfilehash: 8ac7cee2f9959bc75df165d00d3a0a67e1dd9af0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982399"
---
# <a name="error-statement"></a><span data-ttu-id="105ac-102">Error 문</span><span class="sxs-lookup"><span data-stu-id="105ac-102">Error Statement</span></span>
<span data-ttu-id="105ac-103">오류의 발생을 시뮬레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="105ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="105ac-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="105ac-105">요소</span><span class="sxs-lookup"><span data-stu-id="105ac-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="105ac-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="105ac-106">Required.</span></span> <span data-ttu-id="105ac-107">유효한 임의의 오류 번호를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="105ac-108">설명</span><span class="sxs-lookup"><span data-stu-id="105ac-108">Remarks</span></span>  
 <span data-ttu-id="105ac-109">`Error` 문은 이전 버전과 호환성을 위해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="105ac-110">새 코드에서는 개체를 만들 때 특히를 사용 합니다 `Err` 개체의 `Raise` 런타임 오류를 생성 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="105ac-111">경우 `errornumber` 정의 되는 `Error` 속성을 후 오류 처리기를 호출 하는 문을 `Err` 개체는 다음과 같은 기본값이 할당 됩니다:</span><span class="sxs-lookup"><span data-stu-id="105ac-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="105ac-112">속성</span><span class="sxs-lookup"><span data-stu-id="105ac-112">Property</span></span>|<span data-ttu-id="105ac-113">값</span><span class="sxs-lookup"><span data-stu-id="105ac-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="105ac-114">인수로 지정 된 값 `Error` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="105ac-115">유효한 임의의 오류 번호를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="105ac-116">현재 Visual Basic 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="105ac-117">문자열 식의 반환 값에 해당 하는 `Error` 지정 된 함수 `Number`이 문자열이 존재 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="105ac-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="105ac-118">문자열이 없으면 `Description` 길이가 0 인 문자열 포함 ("").</span><span class="sxs-lookup"><span data-stu-id="105ac-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="105ac-119">정규화 된 드라이브, 경로 및 적절 한 Visual Basic 도움말 파일의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="105ac-120">적절 한 Visual Basic 도움말 파일 컨텍스트 ID에 해당 하는 오류에 대 한는 `Number` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="105ac-121">0입니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-121">Zero.</span></span>|  
  
 <span data-ttu-id="105ac-122">오류 처리기가 없거나, 또는 오류 메시지가 생성 되어 표시에서 none을 사용 하는 경우는 `Err` 개체 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="105ac-123">일부 Visual Basic 호스트 응용 프로그램 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="105ac-124">클래스 및 개체를 만들 수 있는지 확인 하려면 호스트 응용 프로그램의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="105ac-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="105ac-125">예제</span><span class="sxs-lookup"><span data-stu-id="105ac-125">Example</span></span>  
 <span data-ttu-id="105ac-126">이 예제에서는 `Error` 문의 오류 번호 11을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="105ac-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="105ac-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="105ac-127">Requirements</span></span>  
 <span data-ttu-id="105ac-128">**네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="105ac-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="105ac-129">**어셈블리:** Visual Basic 런타임 라이브러리(Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="105ac-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="105ac-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="105ac-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="105ac-131">On Error 문</span><span class="sxs-lookup"><span data-stu-id="105ac-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="105ac-132">Resume 문</span><span class="sxs-lookup"><span data-stu-id="105ac-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="105ac-133">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="105ac-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
