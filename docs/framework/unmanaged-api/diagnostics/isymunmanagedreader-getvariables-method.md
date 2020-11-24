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
ms.openlocfilehash: c4341a5ffe557694473ae505590b57d39a27a721
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675895"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="b2b15-102">ISymUnmanagedReader::GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="b2b15-102">ISymUnmanagedReader::GetVariables Method</span></span>

<span data-ttu-id="b2b15-103">부모 및 이름이 지정 된 경우 지역 변수가 아닌 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b15-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b15-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2b15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2b15-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2b15-105">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="b2b15-106">진행 변수의 부모입니다.</span><span class="sxs-lookup"><span data-stu-id="b2b15-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="b2b15-107">[in] `pVars` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b2b15-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="b2b15-108">제한이 에서 반환 된 변수 수를 받는 변수에 대 한 포인터입니다 `pVars` .</span><span class="sxs-lookup"><span data-stu-id="b2b15-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="b2b15-109">제한이 변수를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2b15-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2b15-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="b2b15-110">Return Value</span></span>  

 <span data-ttu-id="b2b15-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2b15-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b15-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2b15-112">Requirements</span></span>  

 <span data-ttu-id="b2b15-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="b2b15-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b15-114">참조</span><span class="sxs-lookup"><span data-stu-id="b2b15-114">See also</span></span>

- [<span data-ttu-id="b2b15-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2b15-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
