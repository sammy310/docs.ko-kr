---
description: '자세히 알아보기: ISymUnmanagedReader:: GetGlobalVariables 메서드'
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
ms.openlocfilehash: 2b017d2a5746942f701cf79d3d29f1eb571dceab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689653"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="3b18c-103">ISymUnmanagedReader::GetGlobalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="3b18c-103">ISymUnmanagedReader::GetGlobalVariables Method</span></span>

<span data-ttu-id="3b18c-104">모든 전역 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b18c-104">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b18c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3b18c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b18c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b18c-106">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="3b18c-107">진행 가 가리키는 버퍼의 길이입니다 `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="3b18c-107">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="3b18c-108">제한이 `ULONG32` 변수를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b18c-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="3b18c-109">제한이 변수를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="3b18c-109">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b18c-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="3b18c-110">Return Value</span></span>  

 <span data-ttu-id="3b18c-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3b18c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b18c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b18c-112">Requirements</span></span>  

 <span data-ttu-id="3b18c-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3b18c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b18c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b18c-114">See also</span></span>

- [<span data-ttu-id="3b18c-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b18c-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
