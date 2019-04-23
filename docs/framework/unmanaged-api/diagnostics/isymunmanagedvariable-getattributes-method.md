---
title: ISymUnmanagedVariable::GetAttributes 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7ba794060330de3934f8d4ca6434b09672d12bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090591"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="661ea-102">ISymUnmanagedVariable::GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="661ea-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="661ea-103">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="661ea-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="661ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="661ea-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="661ea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="661ea-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="661ea-106">[out] 에 대 한 포인터를 `ULONG32` 특성을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="661ea-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="661ea-107">반환된 된 값에 정의 된 값 중 하나로 설정 됩니다는 [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="661ea-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="661ea-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="661ea-108">Return Value</span></span>  
 <span data-ttu-id="661ea-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="661ea-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="661ea-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="661ea-110">Requirements</span></span>  
 <span data-ttu-id="661ea-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="661ea-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661ea-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="661ea-112">See also</span></span>

- [<span data-ttu-id="661ea-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="661ea-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
