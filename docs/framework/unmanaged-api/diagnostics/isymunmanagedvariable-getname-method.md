---
title: ISymUnmanagedVariable::GetName 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e863640e18ca64de084331327e0fa39468b54b60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797542"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="714cc-102">ISymUnmanagedVariable::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="714cc-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="714cc-103">이 변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="714cc-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="714cc-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="714cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="714cc-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="714cc-106">[in] 버퍼의 길이는 `pcchName` 매개 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="714cc-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="714cc-107">[out] 에 대 한 포인터를 `ULONG32` 문자의 null 종료를 포함 하는 이름을 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="714cc-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="714cc-108">[out] 이름을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="714cc-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="714cc-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="714cc-109">Return Value</span></span>  
 <span data-ttu-id="714cc-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="714cc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="714cc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="714cc-111">Requirements</span></span>  
 <span data-ttu-id="714cc-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="714cc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714cc-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="714cc-113">See also</span></span>

- [<span data-ttu-id="714cc-114">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="714cc-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
