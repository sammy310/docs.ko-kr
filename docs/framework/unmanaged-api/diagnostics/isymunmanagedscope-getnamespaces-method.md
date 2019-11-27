---
title: ISymUnmanagedScope::GetNamespaces 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: b765294826a5da4010cdd2db79b50667a6f1cdb4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446307"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="7e7b3-102">ISymUnmanagedScope::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="7e7b3-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="7e7b3-103">이 범위 내에서 사용 되는 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e7b3-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e7b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e7b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e7b3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e7b3-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="7e7b3-106">[in] `namespaces` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7e7b3-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="7e7b3-107">제한이 네임 스페이스를 포함 하는 데 필요한 버퍼 크기를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e7b3-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="7e7b3-108">제한이 네임 스페이스를 받는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e7b3-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e7b3-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="7e7b3-109">Return Value</span></span>  
 <span data-ttu-id="7e7b3-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7e7b3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e7b3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e7b3-111">Requirements</span></span>  
 <span data-ttu-id="7e7b3-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="7e7b3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e7b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e7b3-113">See also</span></span>

- [<span data-ttu-id="7e7b3-114">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e7b3-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
