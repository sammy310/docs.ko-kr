---
description: '자세히 알아보기: ISymUnmanagedVariable:: GetStartOffset 메서드'
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
ms.openlocfilehash: 96ff27cfaf53c7a63c819b1a423e62478cf74832
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762723"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="f49c4-103">ISymUnmanagedVariable::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="f49c4-103">ISymUnmanagedVariable::GetStartOffset Method</span></span>

<span data-ttu-id="f49c4-104">부모 내에서이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f49c4-104">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="f49c4-105">범위 내에 있는 지역 변수인 경우 시작 오프셋은 범위에 대해 정의 된 오프셋에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f49c4-105">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f49c4-106">구문</span><span class="sxs-lookup"><span data-stu-id="f49c4-106">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f49c4-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f49c4-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="f49c4-108">제한이 시작 오프셋을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f49c4-108">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f49c4-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="f49c4-109">Return Value</span></span>  

 <span data-ttu-id="f49c4-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f49c4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f49c4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f49c4-111">Requirements</span></span>  

 <span data-ttu-id="f49c4-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="f49c4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f49c4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f49c4-113">See also</span></span>

- [<span data-ttu-id="f49c4-114">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f49c4-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="f49c4-115">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="f49c4-115">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
