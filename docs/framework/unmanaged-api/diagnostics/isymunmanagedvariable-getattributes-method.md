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
ms.openlocfilehash: f7e71315b5ff99a550ae4a59f3b0d444093dac01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778282"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="df510-102">ISymUnmanagedVariable::GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="df510-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="df510-103">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df510-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df510-104">구문</span><span class="sxs-lookup"><span data-stu-id="df510-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df510-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df510-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="df510-106">[out] 에 대 한 포인터를 `ULONG32` 특성을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="df510-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="df510-107">반환된 된 값에 정의 된 값 중 하나로 설정 됩니다는 [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="df510-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df510-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="df510-108">Return Value</span></span>  
 <span data-ttu-id="df510-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="df510-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df510-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df510-110">Requirements</span></span>  
 <span data-ttu-id="df510-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df510-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df510-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="df510-112">See also</span></span>

- [<span data-ttu-id="df510-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df510-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
