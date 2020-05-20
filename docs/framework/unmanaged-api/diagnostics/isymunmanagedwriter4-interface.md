---
title: ISymUnmanagedWriter4 인터페이스
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609471"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="d40b9-102">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d40b9-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="d40b9-103">ISymUnmanagedWriter4 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d40b9-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d40b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="d40b9-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="d40b9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d40b9-105">Methods</span></span>  
 <span data-ttu-id="d40b9-106">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d40b9-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="d40b9-107">메서드</span><span class="sxs-lookup"><span data-stu-id="d40b9-107">Method</span></span>|<span data-ttu-id="d40b9-108">설명</span><span class="sxs-lookup"><span data-stu-id="d40b9-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d40b9-109">GetDebugInfoWithPadding 메서드</span><span class="sxs-lookup"><span data-stu-id="d40b9-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="d40b9-110">는 [GetDebugInfo 메서드와](isymunmanagedwriter-getdebuginfo-method.md) 동일 하 게 작동 합니다. 단, 경로 문자열은 종료 null 문자 다음에 0으로 채워져 문자열 데이터의 고정 크기를 만듭니다 `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="d40b9-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="d40b9-111">패딩은 경로 문자열 길이 자체가 보다 작은 경우에만 지정 됩니다 `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="d40b9-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="d40b9-112">따라서 PE 파일의 차이점을 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d40b9-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d40b9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d40b9-113">Requirements</span></span>  
 <span data-ttu-id="d40b9-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d40b9-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40b9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d40b9-115">See also</span></span>

- [<span data-ttu-id="d40b9-116">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d40b9-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d40b9-117">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d40b9-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
