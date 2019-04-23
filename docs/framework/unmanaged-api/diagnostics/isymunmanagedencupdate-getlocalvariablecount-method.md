---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a75ca89a3537ce8ee72e8ba24401800eacff20
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153779"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="5d841-102">ISymUnmanagedENCUpdate::GetLocalVariableCount 메서드</span><span class="sxs-lookup"><span data-stu-id="5d841-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="5d841-103">지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d841-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d841-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d841-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d841-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d841-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="5d841-106">[in] 메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5d841-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="5d841-107">[out] 에 대 한 포인터를 `ULONG32` 로컬 변수 수를 포함 하는 데 필요한 버퍼의 문자에서는 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d841-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d841-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5d841-108">Return Value</span></span>  
 <span data-ttu-id="5d841-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5d841-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d841-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d841-110">Requirements</span></span>  
 <span data-ttu-id="5d841-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5d841-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d841-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d841-112">See also</span></span>

- [<span data-ttu-id="5d841-113">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d841-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
