---
title: ISymUnmanagedConstant::GetSignature 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 332d60418c744a9391c7c0afc20248c2239b090c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441622"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="78f84-102">ISymUnmanagedConstant::GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="78f84-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="78f84-103">상수의 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="78f84-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f84-104">구문</span><span class="sxs-lookup"><span data-stu-id="78f84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78f84-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78f84-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="78f84-106">진행 매개 변수가 가리키는 버퍼의 길이입니다 `pcSig` .</span><span class="sxs-lookup"><span data-stu-id="78f84-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="78f84-107">제한이 `ULONG32`서명을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="78f84-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="78f84-108">제한이 서명을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="78f84-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78f84-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="78f84-109">Return Value</span></span>  
 <span data-ttu-id="78f84-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="78f84-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f84-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78f84-111">Requirements</span></span>  
 <span data-ttu-id="78f84-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="78f84-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f84-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78f84-113">See also</span></span>

- [<span data-ttu-id="78f84-114">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78f84-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="78f84-115">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="78f84-115">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="78f84-116">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="78f84-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
