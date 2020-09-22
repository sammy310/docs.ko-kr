---
title: 레코드 길이가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 6967015572b2567f52697f7ddcb1ff594013a2c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869259"
---
# <a name="bad-record-length"></a><span data-ttu-id="9f142-102">레코드 길이가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f142-102">Bad record length</span></span>

<span data-ttu-id="9f142-103">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="9f142-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="9f142-104">, 또는 문에 지정 된 record 변수의 길이가 `FileGet` `FileGetObject` `FilePut` `FilePutObject` 해당 문에 지정 된 길이와 다릅니다 `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="9f142-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="9f142-105">`FilePut`또는 `FilePutObject` 문의 변수가 이거나 가변 길이 문자열을 포함 하는 경우</span><span class="sxs-lookup"><span data-stu-id="9f142-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="9f142-106">또는의 변수가 `FilePut` `FilePutObject` 이거나 `Variant` 형식을 포함 하는 경우</span><span class="sxs-lookup"><span data-stu-id="9f142-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f142-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9f142-107">To correct this error</span></span>  
  
1. <span data-ttu-id="9f142-108">Record 변수의 형식을 정의 하는 사용자 정의 형식에서 고정 길이 변수 크기의 합이 문의 절에 지정 된 값과 동일한 지 확인 합니다 `FileOpen` `Len` .</span><span class="sxs-lookup"><span data-stu-id="9f142-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="9f142-109">`FilePut`또는 문의 변수가 또는 `FilePutObject` 가변 길이 문자열을 포함 하는 경우 가변 길이 문자열이 문의 절에 지정 된 레코드 길이 보다 2 자 이상 길어야 합니다 `Len` `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="9f142-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="9f142-110">또는의 변수가 이거나를 포함 하는 경우 `FilePut` `FilePutObject` `Variant` 가변 길이 문자열이 문의 절에 지정 된 레코드 길이 보다 4 바이트 이상 길어야 합니다 `Len` `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="9f142-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f142-111">참조</span><span class="sxs-lookup"><span data-stu-id="9f142-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
