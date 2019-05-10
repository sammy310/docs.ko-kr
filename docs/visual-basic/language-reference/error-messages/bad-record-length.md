---
title: 레코드 길이가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 7ec0a8c27f425ec717bca5d45d5dfd2b601c11d5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665729"
---
# <a name="bad-record-length"></a><span data-ttu-id="ea8f3-102">레코드 길이가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-102">Bad record length</span></span>
<span data-ttu-id="ea8f3-103">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="ea8f3-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="ea8f3-104">에 지정 된 레코드 변수의 길이 `FileGet`, `FileGetObject`, `FilePut` 또는 `FilePutObject` 문은 해당에 지정 된 길이에서 다른 `FileOpen` 문.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="ea8f3-105">변수를 `FilePut` 또는 `FilePutObject` 문이 하거나 가변 길이 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="ea8f3-106">변수를 `FilePut` 또는 `FilePutObject` 되거나 포함 하는 `Variant` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea8f3-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ea8f3-107">To correct this error</span></span>  
  
1. <span data-ttu-id="ea8f3-108">값에서 설명한 것 처럼 레코드 변수의 형식을 정의 하는 사용자 정의 형식에서 고정 길이 변수의 크기의 합이 동일한 지 확인 합니다 `FileOpen` 문의 `Len` 절.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="ea8f3-109">경우에서 변수를 `FilePut` 또는 `FilePutObject` 문 또는 가변 길이 문자열을 포함에 가변 길이 문자열에 지정 된 레코드 길이 보다 짧은 2 개 이상의 문자 인지 확인 합니다 `Len` 절을 `FileOpen` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="ea8f3-110">경우에서 변수를 `FilePut` 또는 `FilePutObject` 되거나 포함 하는 `Variant` 가변 길이 문자열에 지정 된 레코드 길이 보다 짧으면 4 바이트 이상 인지 확인 합니다 `Len` 절은 `FileOpen` 문을.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8f3-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea8f3-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
