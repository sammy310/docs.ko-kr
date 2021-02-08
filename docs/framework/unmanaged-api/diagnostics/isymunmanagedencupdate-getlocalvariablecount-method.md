---
description: '자세히 알아보기: ISymUnmanagedENCUpdate:: GetLocalVariableCount 메서드'
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
ms.openlocfilehash: ab75ba0b0dda5722aebdbdc8b9a242cc90b0ac11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790154"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="89746-103">ISymUnmanagedENCUpdate::GetLocalVariableCount 메서드</span><span class="sxs-lookup"><span data-stu-id="89746-103">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>

<span data-ttu-id="89746-104">지역 변수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89746-104">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89746-105">구문</span><span class="sxs-lookup"><span data-stu-id="89746-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89746-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89746-106">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="89746-107">진행 메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="89746-107">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="89746-108">제한이 `ULONG32` 지역 변수 수를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="89746-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89746-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="89746-109">Return Value</span></span>  

 <span data-ttu-id="89746-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="89746-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89746-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89746-111">Requirements</span></span>  

 <span data-ttu-id="89746-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="89746-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89746-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89746-113">See also</span></span>

- [<span data-ttu-id="89746-114">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89746-114">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
