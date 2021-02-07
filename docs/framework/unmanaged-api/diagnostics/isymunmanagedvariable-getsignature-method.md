---
description: '자세히 알아보기: ISymUnmanagedVariable:: GetSignature 메서드'
title: ISymUnmanagedVariable::GetSignature 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: 6e8242581cf2d59563b6193ed7c7686292cbf775
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762736"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="18c4e-103">ISymUnmanagedVariable::GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="18c4e-103">ISymUnmanagedVariable::GetSignature Method</span></span>

<span data-ttu-id="18c4e-104">이 변수의 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18c4e-104">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c4e-105">구문</span><span class="sxs-lookup"><span data-stu-id="18c4e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18c4e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18c4e-106">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="18c4e-107">진행 매개 변수가 가리키는 버퍼의 길이입니다 `sig` .</span><span class="sxs-lookup"><span data-stu-id="18c4e-107">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="18c4e-108">제한이 `ULONG32` 서명을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18c4e-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="18c4e-109">제한이 서명을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="18c4e-109">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18c4e-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="18c4e-110">Return Value</span></span>  

 <span data-ttu-id="18c4e-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18c4e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18c4e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18c4e-112">Requirements</span></span>  

 <span data-ttu-id="18c4e-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="18c4e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c4e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18c4e-114">See also</span></span>

- [<span data-ttu-id="18c4e-115">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18c4e-115">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
