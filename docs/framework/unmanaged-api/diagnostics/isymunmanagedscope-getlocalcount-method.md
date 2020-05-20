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
ms.openlocfilehash: 9ffba23e3821c48c9b0708e4b6b617db4ddc5959
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611265"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="126f7-102">ISymUnmanagedScope::GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="126f7-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="126f7-103">이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="126f7-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="126f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="126f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="126f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="126f7-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="126f7-106">제한이 `ULONG32`지역 변수의 개수를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="126f7-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="126f7-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="126f7-107">Return Value</span></span>  
 <span data-ttu-id="126f7-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="126f7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="126f7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="126f7-109">Requirements</span></span>  
 <span data-ttu-id="126f7-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="126f7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126f7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="126f7-111">See also</span></span>

- [<span data-ttu-id="126f7-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="126f7-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
