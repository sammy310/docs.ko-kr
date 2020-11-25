---
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
ms.openlocfilehash: 791b92c30fc2bf3d506113620b59ba20015e077e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725822"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="65cbc-102">ISymUnmanagedVariable::GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="65cbc-102">ISymUnmanagedVariable::GetSignature Method</span></span>

<span data-ttu-id="65cbc-103">이 변수의 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65cbc-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65cbc-104">구문</span><span class="sxs-lookup"><span data-stu-id="65cbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65cbc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65cbc-105">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="65cbc-106">진행 매개 변수가 가리키는 버퍼의 길이입니다 `sig` .</span><span class="sxs-lookup"><span data-stu-id="65cbc-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="65cbc-107">제한이 `ULONG32` 서명을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="65cbc-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="65cbc-108">제한이 서명을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="65cbc-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65cbc-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="65cbc-109">Return Value</span></span>  

 <span data-ttu-id="65cbc-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="65cbc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65cbc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65cbc-111">Requirements</span></span>  

 <span data-ttu-id="65cbc-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="65cbc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65cbc-113">참조</span><span class="sxs-lookup"><span data-stu-id="65cbc-113">See also</span></span>

- [<span data-ttu-id="65cbc-114">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65cbc-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
