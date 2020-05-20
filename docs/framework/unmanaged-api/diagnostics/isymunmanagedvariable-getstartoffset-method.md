---
title: ISymUnmanagedVariable::GetStartOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610368"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="2dd60-102">ISymUnmanagedVariable::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd60-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="2dd60-103">부모 내에서이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2dd60-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="2dd60-104">범위 내에 있는 지역 변수인 경우 시작 오프셋은 범위에 대해 정의 된 오프셋에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dd60-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd60-105">구문</span><span class="sxs-lookup"><span data-stu-id="2dd60-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dd60-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dd60-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2dd60-107">제한이 시작 오프셋을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2dd60-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2dd60-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="2dd60-108">Return Value</span></span>  
 <span data-ttu-id="2dd60-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2dd60-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dd60-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dd60-110">Requirements</span></span>  
 <span data-ttu-id="2dd60-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2dd60-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd60-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dd60-112">See also</span></span>

- [<span data-ttu-id="2dd60-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dd60-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="2dd60-114">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd60-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
