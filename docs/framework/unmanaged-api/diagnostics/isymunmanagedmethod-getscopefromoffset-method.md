---
description: '자세히 알아보기: ISymUnmanagedMethod:: GetScopeFromOffset 메서드'
title: ISymUnmanagedMethod::GetScopeFromOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 87dd1f1732ec5d7c8669dbc2bf73b0b6128aafa1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721322"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="1ae4b-103">ISymUnmanagedMethod::GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="1ae4b-103">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>

<span data-ttu-id="1ae4b-104">이 메서드 내에서 지정 된 오프셋을 둘러싸는 가장 바깥쪽 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ae4b-104">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="1ae4b-105">이를 사용 하 여 지역 변수 검색을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae4b-105">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae4b-106">구문</span><span class="sxs-lookup"><span data-stu-id="1ae4b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ae4b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ae4b-107">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="1ae4b-108">진행 `ULONG` 오프셋을 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae4b-108">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1ae4b-109">제한이 반환 된 [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae4b-109">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ae4b-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="1ae4b-110">Return Value</span></span>  

 <span data-ttu-id="1ae4b-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae4b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ae4b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ae4b-112">Requirements</span></span>  

 <span data-ttu-id="1ae4b-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="1ae4b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae4b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ae4b-114">See also</span></span>

- [<span data-ttu-id="1ae4b-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ae4b-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
