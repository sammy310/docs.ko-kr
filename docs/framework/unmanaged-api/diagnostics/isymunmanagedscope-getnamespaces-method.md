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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d2c64d7ead2f7ce3d76b40f4fdc604506ee85561
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777885"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="a7789-102">ISymUnmanagedScope::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="a7789-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="a7789-103">이 범위 내에서 사용 되 고 있는 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7789-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7789-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7789-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7789-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7789-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="a7789-106">[in] `namespaces` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a7789-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="a7789-107">[out] 에 대 한 포인터를 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7789-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="a7789-108">[out] 네임 스페이스를 수신 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a7789-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7789-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7789-109">Return Value</span></span>  
 <span data-ttu-id="a7789-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a7789-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7789-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7789-111">Requirements</span></span>  
 <span data-ttu-id="a7789-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a7789-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7789-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7789-113">See also</span></span>

- [<span data-ttu-id="a7789-114">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7789-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
