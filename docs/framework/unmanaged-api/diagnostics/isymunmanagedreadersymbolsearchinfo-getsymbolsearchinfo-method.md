---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
ms.openlocfilehash: 402b5b4bc9734be59ff342a4f86f2c4a1ed23b5f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446402"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="a3e15-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="a3e15-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="a3e15-103">기호 검색 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3e15-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e15-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3e15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3e15-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3e15-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="a3e15-106">진행 `rgpSearchInfo`크기를 나타내는 `ULONG32`입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e15-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="a3e15-107">제한이 검색 정보를 포함 하는 데 필요한 버퍼 크기를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e15-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="a3e15-108">제한이 반환 된 [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e15-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3e15-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a3e15-109">Return Value</span></span>  
 <span data-ttu-id="a3e15-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e15-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3e15-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3e15-111">Requirements</span></span>  
 <span data-ttu-id="a3e15-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a3e15-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e15-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3e15-113">See also</span></span>

- [<span data-ttu-id="a3e15-114">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3e15-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
