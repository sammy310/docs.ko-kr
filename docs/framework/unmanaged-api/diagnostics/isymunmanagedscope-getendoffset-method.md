---
title: ISymUnmanagedScope::GetEndOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e28a351b6d47d14f171b9e760b2fa2c6755e3f8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158589"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="ed02d-102">ISymUnmanagedScope::GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="ed02d-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="ed02d-103">이 범위의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed02d-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed02d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed02d-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed02d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed02d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ed02d-106">[out] 에 대 한 포인터를 `ULONG32` 를 받는 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ed02d-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed02d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ed02d-107">Return Value</span></span>  
 <span data-ttu-id="ed02d-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed02d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed02d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed02d-109">Requirements</span></span>  
 <span data-ttu-id="ed02d-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ed02d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed02d-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed02d-111">See also</span></span>

- [<span data-ttu-id="ed02d-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed02d-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="ed02d-113">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="ed02d-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
