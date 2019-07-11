---
title: ISymUnmanagedWriter::OpenMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25178b5ea27aac7229ab51a167283d955b89addc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777268"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="097ed-102">ISymUnmanagedWriter::OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="097ed-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="097ed-103">정보는 기호를 내보내는 메서드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="097ed-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="097ed-104">지정된 된 메서드 호출 시퀀스 위치, 매개 변수 및 어휘 범위를 정의 하는 최신 방법이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="097ed-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="097ed-105">전체 메서드 주위에 암시적 어휘 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097ed-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="097ed-106">이전에 닫힌 하는 메서드를 다시 열 때 해당 메서드에 대 한 모든 이전에 정의 된 기호를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="097ed-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="097ed-107">한 번에 하나만 open 메서드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="097ed-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097ed-108">구문</span><span class="sxs-lookup"><span data-stu-id="097ed-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="097ed-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="097ed-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="097ed-110">[in] 열려는 메서드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="097ed-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="097ed-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="097ed-111">Return Value</span></span>  
 <span data-ttu-id="097ed-112">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="097ed-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="097ed-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="097ed-113">Requirements</span></span>  
 <span data-ttu-id="097ed-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="097ed-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097ed-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="097ed-115">See also</span></span>

- [<span data-ttu-id="097ed-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="097ed-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="097ed-117">CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="097ed-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="097ed-118">OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="097ed-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
