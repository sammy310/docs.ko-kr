---
title: ISymUnmanagedScope::GetLocalCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b3c9c637bdaa0d0e18dbfd9655790ff5ebd46f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141845"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="a9d1b-102">ISymUnmanagedScope::GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="a9d1b-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="a9d1b-103">이 범위 내에 정의 된 로컬 변수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9d1b-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d1b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9d1b-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9d1b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9d1b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a9d1b-106">[out] 에 대 한 포인터를 `ULONG32` 로컬 변수 수를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d1b-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9d1b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a9d1b-107">Return Value</span></span>  
 <span data-ttu-id="a9d1b-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d1b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d1b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9d1b-109">Requirements</span></span>  
 <span data-ttu-id="a9d1b-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a9d1b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d1b-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="a9d1b-111">See also</span></span>

- [<span data-ttu-id="a9d1b-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9d1b-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
