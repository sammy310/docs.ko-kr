---
title: ISymUnmanagedScope::GetChildren 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: c6d21f40c260890c9c88dcdfccd7e31161024ba3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614866"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="74417-102">ISymUnmanagedScope::GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="74417-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="74417-103">이 범위의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74417-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74417-104">구문</span><span class="sxs-lookup"><span data-stu-id="74417-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74417-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74417-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="74417-106">진행 `ULONG32`배열의 크기를 나타내는입니다 `children` .</span><span class="sxs-lookup"><span data-stu-id="74417-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="74417-107">제한이 `ULONG32`자식을 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74417-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="74417-108">제한이 반환 된 자식의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="74417-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74417-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="74417-109">Return Value</span></span>  
 <span data-ttu-id="74417-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="74417-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74417-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74417-111">Requirements</span></span>  
 <span data-ttu-id="74417-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="74417-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74417-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74417-113">See also</span></span>

- [<span data-ttu-id="74417-114">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74417-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="74417-115">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="74417-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
