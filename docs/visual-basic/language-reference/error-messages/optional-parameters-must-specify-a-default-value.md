---
title: 선택적 매개 변수는 기본값을 지정해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: b32c150f0faf4a9dcec3cec7620c3a9c050f6f20
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696877"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="f949d-102">선택적 매개 변수는 기본값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f949d-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="f949d-103">선택적 매개 변수는 호출 하는 프로시저에서 매개 변수를 제공 하지 않는 경우 사용할 수 있는 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f949d-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="f949d-104">**오류 ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="f949d-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f949d-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f949d-105">To correct this error</span></span>  
  
- <span data-ttu-id="f949d-106">선택적 매개 변수의 기본값 지정 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f949d-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```vb  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f949d-107">참조</span><span class="sxs-lookup"><span data-stu-id="f949d-107">See also</span></span>

- [<span data-ttu-id="f949d-108">선택 사항</span><span class="sxs-lookup"><span data-stu-id="f949d-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
