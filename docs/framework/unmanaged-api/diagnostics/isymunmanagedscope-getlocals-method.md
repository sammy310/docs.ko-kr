---
description: '자세히 알아보기: ISymUnmanagedScope:: GetLocals 메서드'
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
ms.openlocfilehash: 6b20d8a79e826be0bd191d46e794f8dad45c4810
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763412"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="c035c-103">ISymUnmanagedScope::GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="c035c-103">ISymUnmanagedScope::GetLocals Method</span></span>

<span data-ttu-id="c035c-104">이 범위 내에 정의 된 지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c035c-104">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c035c-105">구문</span><span class="sxs-lookup"><span data-stu-id="c035c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c035c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c035c-106">Parameters</span></span>  

 `cLocals`  
 <span data-ttu-id="c035c-107">진행 `ULONG32` 배열의 크기를 나타내는입니다 `locals` .</span><span class="sxs-lookup"><span data-stu-id="c035c-107">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="c035c-108">제한이 `ULONG32` 지역 변수를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c035c-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="c035c-109">제한이 지역 변수를 받는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c035c-109">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c035c-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="c035c-110">Return Value</span></span>  

 <span data-ttu-id="c035c-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c035c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c035c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c035c-112">Requirements</span></span>  

 <span data-ttu-id="c035c-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c035c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c035c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c035c-114">See also</span></span>

- [<span data-ttu-id="c035c-115">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c035c-115">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
