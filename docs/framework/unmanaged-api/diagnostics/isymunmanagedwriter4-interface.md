---
title: ISymUnmanagedWriter4 인터페이스
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725809"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="41707-102">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41707-102">ISymUnmanagedWriter4 Interface</span></span>

<span data-ttu-id="41707-103">ISymUnmanagedWriter4 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="41707-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41707-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41707-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="41707-105">메서드</span><span class="sxs-lookup"><span data-stu-id="41707-105">Methods</span></span>  

 <span data-ttu-id="41707-106">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41707-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="41707-107">메서드</span><span class="sxs-lookup"><span data-stu-id="41707-107">Method</span></span>|<span data-ttu-id="41707-108">설명</span><span class="sxs-lookup"><span data-stu-id="41707-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41707-109">GetDebugInfoWithPadding 메서드</span><span class="sxs-lookup"><span data-stu-id="41707-109">GetDebugInfoWithPadding Method</span></span>](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="41707-110">는 [GetDebugInfo 메서드와](isymunmanagedwriter-getdebuginfo-method.md) 동일 하 게 작동 합니다. 단, 경로 문자열은 종료 null 문자 다음에 0으로 채워져 문자열 데이터의 고정 크기를 만듭니다 `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="41707-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="41707-111">패딩은 경로 문자열 길이 자체가 보다 작은 경우에만 지정 됩니다 `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="41707-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="41707-112">따라서 PE 파일의 차이점을 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41707-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41707-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41707-113">Requirements</span></span>  

 <span data-ttu-id="41707-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="41707-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41707-115">참조</span><span class="sxs-lookup"><span data-stu-id="41707-115">See also</span></span>

- [<span data-ttu-id="41707-116">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41707-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="41707-117">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41707-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
