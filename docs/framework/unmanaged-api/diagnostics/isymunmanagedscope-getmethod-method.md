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
ms.openlocfilehash: 75d5638a6f01ba9569a03e5255a7217371c9d177
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725939"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="a75c3-102">ISymUnmanagedScope::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a75c3-102">ISymUnmanagedScope::GetMethod Method</span></span>

<span data-ttu-id="a75c3-103">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a75c3-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a75c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a75c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a75c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a75c3-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="a75c3-106">제한이 반환 된 [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a75c3-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a75c3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a75c3-107">Return Value</span></span>  

 <span data-ttu-id="a75c3-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a75c3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a75c3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a75c3-109">Requirements</span></span>  

 <span data-ttu-id="a75c3-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a75c3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75c3-111">참조</span><span class="sxs-lookup"><span data-stu-id="a75c3-111">See also</span></span>

- [<span data-ttu-id="a75c3-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a75c3-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
