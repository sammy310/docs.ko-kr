---
description: '자세히 알아보기: ISymUnmanagedScope:: GetParent 메서드'
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
ms.openlocfilehash: c6a056c828bfaefd171ef3f0c546d93d30fb6863
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763334"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="e99f4-103">ISymUnmanagedScope::GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="e99f4-103">ISymUnmanagedScope::GetParent Method</span></span>

<span data-ttu-id="e99f4-104">이 범위의 부모 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e99f4-104">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e99f4-105">구문</span><span class="sxs-lookup"><span data-stu-id="e99f4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e99f4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e99f4-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="e99f4-107">제한이 반환 된 [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e99f4-107">[out] A pointer to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e99f4-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="e99f4-108">Return Value</span></span>  

 <span data-ttu-id="e99f4-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e99f4-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e99f4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e99f4-110">Requirements</span></span>  

 <span data-ttu-id="e99f4-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="e99f4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99f4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e99f4-112">See also</span></span>

- [<span data-ttu-id="e99f4-113">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e99f4-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="e99f4-114">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="e99f4-114">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)
