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
ms.openlocfilehash: 299787ea4eb8a5c25bdab64ad08445839c9f24d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707544"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="05736-102">ISymUnmanagedReader::GetGlobalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="05736-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>

<span data-ttu-id="05736-103">모든 전역 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="05736-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05736-104">구문</span><span class="sxs-lookup"><span data-stu-id="05736-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05736-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05736-105">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="05736-106">진행 가 가리키는 버퍼의 길이입니다 `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="05736-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="05736-107">제한이 `ULONG32` 변수를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="05736-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="05736-108">제한이 변수를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="05736-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05736-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="05736-109">Return Value</span></span>  

 <span data-ttu-id="05736-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="05736-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05736-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05736-111">Requirements</span></span>  

 <span data-ttu-id="05736-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="05736-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05736-113">참조</span><span class="sxs-lookup"><span data-stu-id="05736-113">See also</span></span>

- [<span data-ttu-id="05736-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05736-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
