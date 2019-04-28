---
title: ISymUnmanagedReader::GetVariables 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 846ff76fb1073394cc27597c9a2015148581cc70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670003"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="2b9f9-102">ISymUnmanagedReader::GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="2b9f9-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="2b9f9-103">해당 부모와 이름을 지정 하는 로컬이 아닌 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9f9-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b9f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b9f9-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b9f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b9f9-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="2b9f9-106">[in] 부모 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9f9-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="2b9f9-107">[in] `pVars` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9f9-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="2b9f9-108">[out] 반환 된 변수의 수를 받는 변수의에 대 한 포인터 `pVars`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9f9-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="2b9f9-109">[out] 변수를 받는 변수의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9f9-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b9f9-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2b9f9-110">Return Value</span></span>  
 <span data-ttu-id="2b9f9-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9f9-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b9f9-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b9f9-112">Requirements</span></span>  
 <span data-ttu-id="2b9f9-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2b9f9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b9f9-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b9f9-114">See also</span></span>

- [<span data-ttu-id="2b9f9-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b9f9-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
