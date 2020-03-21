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
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176619"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="dd283-102">ISymUnmanagedScope2::GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="dd283-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="dd283-103">이 범위 내에서 정의된 로컬 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd283-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd283-104">구문</span><span class="sxs-lookup"><span data-stu-id="dd283-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd283-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd283-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="dd283-106">【인】 매개 변수가 가리키는 `pcConstants` 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="dd283-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="dd283-107">【아웃】 상수를 포함 `ULONG32` 하는 데 필요한 버퍼의 크기(문자)를 받는 a에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dd283-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="dd283-108">【아웃】 상수를 저장하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="dd283-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd283-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="dd283-109">Return Value</span></span>  
 <span data-ttu-id="dd283-110">메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL 또는 다른 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd283-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd283-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd283-111">Requirements</span></span>  
 <span data-ttu-id="dd283-112">**헤더:** 코르심.idl, 코르심.h</span><span class="sxs-lookup"><span data-stu-id="dd283-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd283-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd283-113">See also</span></span>

- [<span data-ttu-id="dd283-114">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd283-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
