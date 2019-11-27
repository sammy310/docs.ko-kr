---
title: ISymUnmanagedScope::GetMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: 348a8cebe0fd746f3ae490484ffcca2fcb77684b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446320"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="eebfa-102">ISymUnmanagedScope::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="eebfa-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="eebfa-103">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eebfa-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eebfa-104">구문</span><span class="sxs-lookup"><span data-stu-id="eebfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eebfa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eebfa-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="eebfa-106">제한이 반환 된 [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eebfa-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eebfa-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="eebfa-107">Return Value</span></span>  
 <span data-ttu-id="eebfa-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="eebfa-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eebfa-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eebfa-109">Requirements</span></span>  
 <span data-ttu-id="eebfa-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="eebfa-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eebfa-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eebfa-111">See also</span></span>

- [<span data-ttu-id="eebfa-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eebfa-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
