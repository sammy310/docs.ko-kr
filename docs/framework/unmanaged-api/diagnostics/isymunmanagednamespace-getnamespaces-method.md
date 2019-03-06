---
title: ISymUnmanagedNamespace::GetNamespaces 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8284b23f5d36f7b3405bfff706e0ee7f0e32a042
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479937"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="b2b02-102">ISymUnmanagedNamespace::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="b2b02-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="b2b02-103">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2b02-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b02-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2b02-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2b02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2b02-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="b2b02-106">[in] A `ULONG32` 의 크기를 나타내는 `namespaces` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b2b02-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="b2b02-107">[out] 에 대 한 포인터를 `ULONG32` 문자 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b02-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="b2b02-108">[out] 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2b02-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2b02-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="b2b02-109">Return Value</span></span>  
 <span data-ttu-id="b2b02-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2b02-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b02-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2b02-111">Requirements</span></span>  
 <span data-ttu-id="b2b02-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2b02-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b02-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2b02-113">See also</span></span>
- [<span data-ttu-id="b2b02-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2b02-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
