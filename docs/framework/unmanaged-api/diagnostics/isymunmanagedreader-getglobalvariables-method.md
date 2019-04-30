---
title: ISymUnmanagedReader::GetGlobalVariables 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e778a5a7baed52941a7f4b990b34d31f8ca84c24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986390"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="89e63-102">ISymUnmanagedReader::GetGlobalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="89e63-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="89e63-103">모든 전역 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="89e63-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e63-104">구문</span><span class="sxs-lookup"><span data-stu-id="89e63-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e63-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89e63-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="89e63-106">[in] 가리키는 버퍼의 길이 `pcVars`입니다.</span><span class="sxs-lookup"><span data-stu-id="89e63-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="89e63-107">[out] 에 대 한 포인터를 `ULONG32` 변수를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="89e63-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="89e63-108">[out] 변수를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="89e63-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89e63-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="89e63-109">Return Value</span></span>  
 <span data-ttu-id="89e63-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="89e63-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e63-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89e63-111">Requirements</span></span>  
 <span data-ttu-id="89e63-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="89e63-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e63-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="89e63-113">See also</span></span>

- [<span data-ttu-id="89e63-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89e63-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
