---
title: ISymUnmanagedScope2::GetConstants 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: f558d209d13fae93bd3a6f5e0e653afb91371a6a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615334"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="52344-102">ISymUnmanagedScope2::GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="52344-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="52344-103">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52344-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52344-104">구문</span><span class="sxs-lookup"><span data-stu-id="52344-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52344-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52344-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="52344-106">진행 매개 변수가 가리키는 버퍼의 길이입니다 `pcConstants` .</span><span class="sxs-lookup"><span data-stu-id="52344-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="52344-107">제한이 `ULONG32`상수를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="52344-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="52344-108">제한이 상수를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="52344-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52344-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="52344-109">Return Value</span></span>  
 <span data-ttu-id="52344-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="52344-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52344-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52344-111">Requirements</span></span>  
 <span data-ttu-id="52344-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="52344-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52344-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52344-113">See also</span></span>

- [<span data-ttu-id="52344-114">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52344-114">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
