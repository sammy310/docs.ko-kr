---
title: ISymUnmanagedScope::GetStartOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 9d1ee82f24e1908af1998e424006415af3134456
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446279"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="a2341-102">ISymUnmanagedScope::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="a2341-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="a2341-103">이 범위의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2341-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2341-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2341-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2341-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2341-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a2341-106">제한이 시작 오프셋을 포함 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a2341-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2341-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a2341-107">Return Value</span></span>  
 <span data-ttu-id="a2341-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a2341-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2341-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2341-109">Requirements</span></span>  
 <span data-ttu-id="a2341-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a2341-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2341-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2341-111">See also</span></span>

- [<span data-ttu-id="a2341-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2341-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="a2341-113">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="a2341-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
