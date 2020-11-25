---
title: ISymUnmanagedScope::GetLocals 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 3a2045466340f92dd8421090c74a442068e8bfaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731412"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="d4d86-102">ISymUnmanagedScope::GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="d4d86-102">ISymUnmanagedScope::GetLocals Method</span></span>

<span data-ttu-id="d4d86-103">이 범위 내에 정의 된 지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4d86-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d86-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4d86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4d86-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4d86-105">Parameters</span></span>  

 `cLocals`  
 <span data-ttu-id="d4d86-106">진행 `ULONG32` 배열의 크기를 나타내는입니다 `locals` .</span><span class="sxs-lookup"><span data-stu-id="d4d86-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="d4d86-107">제한이 `ULONG32` 지역 변수를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d86-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="d4d86-108">제한이 지역 변수를 받는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d86-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4d86-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d4d86-109">Return Value</span></span>  

 <span data-ttu-id="d4d86-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d86-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4d86-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4d86-111">Requirements</span></span>  

 <span data-ttu-id="d4d86-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d4d86-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d86-113">참조</span><span class="sxs-lookup"><span data-stu-id="d4d86-113">See also</span></span>

- [<span data-ttu-id="d4d86-114">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4d86-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
