---
description: '자세히 알아보기: ISymUnmanagedENCUpdate:: GetLocalVariables 메서드'
title: ISymUnmanagedENCUpdate::GetLocalVariables 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: bc034603dd6a09ea78dad789e11ea951d65e839b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721465"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="0d50f-103">ISymUnmanagedENCUpdate::GetLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="0d50f-103">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>

<span data-ttu-id="0d50f-104">지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d50f-104">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d50f-105">구문</span><span class="sxs-lookup"><span data-stu-id="0d50f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d50f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d50f-106">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="0d50f-107">진행 메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0d50f-107">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="0d50f-108">진행 `ULONG` 매개 변수의 크기를 나타내는입니다 `rgLocals` .</span><span class="sxs-lookup"><span data-stu-id="0d50f-108">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="0d50f-109">제한이 반환 된 [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) 인스턴스의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0d50f-109">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0d50f-110">제한이 `ULONG` 로컬을 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다 `rgLocals` .</span><span class="sxs-lookup"><span data-stu-id="0d50f-110">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d50f-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="0d50f-111">Return Value</span></span>  

 <span data-ttu-id="0d50f-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0d50f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d50f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d50f-113">Requirements</span></span>  

 <span data-ttu-id="0d50f-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="0d50f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d50f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d50f-115">See also</span></span>

- [<span data-ttu-id="0d50f-116">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d50f-116">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
