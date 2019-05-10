---
title: 선택적 매개 변수는 기본값을 지정해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 0f501b518d5b3f2d48ced33885da2afd353c609e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665684"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="74911-102">선택적 매개 변수는 기본값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74911-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="74911-103">선택적 매개 변수는 매개 변수가 없는 호출 프로시저에서 제공 하는 경우 사용할 수 있는 기본 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74911-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="74911-104">**오류 ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="74911-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="74911-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="74911-105">To correct this error</span></span>  
  
- <span data-ttu-id="74911-106">선택적 매개 변수; 기본값 지정 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="74911-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="74911-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="74911-107">See also</span></span>

- [<span data-ttu-id="74911-108">선택 사항</span><span class="sxs-lookup"><span data-stu-id="74911-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
