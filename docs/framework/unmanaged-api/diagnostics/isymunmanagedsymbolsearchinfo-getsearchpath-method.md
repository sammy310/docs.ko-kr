---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 649f44bd7966b9ca89d2d040b7eede662404aa0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093555"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="0352b-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="0352b-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="0352b-103">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0352b-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0352b-104">구문</span><span class="sxs-lookup"><span data-stu-id="0352b-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0352b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0352b-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="0352b-106">[out] 에 대 한 포인터를 `ULONG32` 문자 검색 경로 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0352b-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0352b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0352b-107">Return Value</span></span>  
 <span data-ttu-id="0352b-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0352b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0352b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0352b-109">Requirements</span></span>  
 <span data-ttu-id="0352b-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0352b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0352b-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="0352b-111">See also</span></span>

- [<span data-ttu-id="0352b-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0352b-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
