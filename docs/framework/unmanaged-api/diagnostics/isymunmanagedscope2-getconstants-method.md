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
ms.openlocfilehash: df42e58a9bb3bf00b3fa4df45086dc2219658e25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725848"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="1ff7b-102">ISymUnmanagedScope2::GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="1ff7b-102">ISymUnmanagedScope2::GetConstants Method</span></span>

<span data-ttu-id="1ff7b-103">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ff7b-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ff7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ff7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ff7b-105">Parameters</span></span>  

 `cConstants`  
 <span data-ttu-id="1ff7b-106">진행 매개 변수가 가리키는 버퍼의 길이입니다 `pcConstants` .</span><span class="sxs-lookup"><span data-stu-id="1ff7b-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="1ff7b-107">제한이 `ULONG32` 상수를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff7b-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="1ff7b-108">제한이 상수를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff7b-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ff7b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ff7b-109">Return Value</span></span>  

 <span data-ttu-id="1ff7b-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff7b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ff7b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ff7b-111">Requirements</span></span>  

 <span data-ttu-id="1ff7b-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="1ff7b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff7b-113">참조</span><span class="sxs-lookup"><span data-stu-id="1ff7b-113">See also</span></span>

- [<span data-ttu-id="1ff7b-114">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ff7b-114">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
