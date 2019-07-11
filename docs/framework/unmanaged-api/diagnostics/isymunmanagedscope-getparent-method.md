---
title: ISymUnmanagedScope::GetParent 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78a0f4b1c111e7978af0259f684402bb98566272
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777865"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="df9c2-102">ISymUnmanagedScope::GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="df9c2-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="df9c2-103">이 범위의 상위 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df9c2-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df9c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="df9c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df9c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df9c2-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="df9c2-106">[out] 반환 된 포인터 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="df9c2-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df9c2-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="df9c2-107">Return Value</span></span>  
 <span data-ttu-id="df9c2-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="df9c2-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df9c2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df9c2-109">Requirements</span></span>  
 <span data-ttu-id="df9c2-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df9c2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9c2-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="df9c2-111">See also</span></span>

- [<span data-ttu-id="df9c2-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df9c2-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="df9c2-113">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="df9c2-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
