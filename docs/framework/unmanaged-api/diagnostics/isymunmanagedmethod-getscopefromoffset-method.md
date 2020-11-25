---
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
ms.openlocfilehash: cf2784ce0ac6e614e75a341660808b9fe03ada0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699445"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="ac46d-102">ISymUnmanagedMethod::GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="ac46d-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>

<span data-ttu-id="ac46d-103">이 메서드 내에서 지정 된 오프셋을 둘러싸는 가장 바깥쪽 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ac46d-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="ac46d-104">이를 사용 하 여 지역 변수 검색을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac46d-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac46d-105">구문</span><span class="sxs-lookup"><span data-stu-id="ac46d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac46d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac46d-106">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="ac46d-107">진행 `ULONG` 오프셋을 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="ac46d-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ac46d-108">제한이 반환 된 [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac46d-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac46d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ac46d-109">Return Value</span></span>  

 <span data-ttu-id="ac46d-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ac46d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac46d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac46d-111">Requirements</span></span>  

 <span data-ttu-id="ac46d-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ac46d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac46d-113">참조</span><span class="sxs-lookup"><span data-stu-id="ac46d-113">See also</span></span>

- [<span data-ttu-id="ac46d-114">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac46d-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
