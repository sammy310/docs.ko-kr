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
ms.openlocfilehash: 95ae081d61200e4fd020609a4d23783f265d2cc6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615360"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="bf95b-102">ISymUnmanagedScope::GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="bf95b-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="bf95b-103">이 범위의 부모 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bf95b-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf95b-104">구문</span><span class="sxs-lookup"><span data-stu-id="bf95b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf95b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf95b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bf95b-106">제한이 반환 된 [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf95b-106">[out] A pointer to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf95b-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="bf95b-107">Return Value</span></span>  
 <span data-ttu-id="bf95b-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bf95b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf95b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf95b-109">Requirements</span></span>  
 <span data-ttu-id="bf95b-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="bf95b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf95b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf95b-111">See also</span></span>

- [<span data-ttu-id="bf95b-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf95b-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="bf95b-113">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="bf95b-113">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)
