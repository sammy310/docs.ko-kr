---
description: '자세히 알아보기: ISymUnmanagedReaderSymbolSearchInfo:: Get기호 Searchinfo 메서드'
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
ms.openlocfilehash: e14f78d6736684205b3f86150ce1fbb44a8112b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763607"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="6f717-103">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="6f717-103">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>

<span data-ttu-id="6f717-104">기호 검색 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-104">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f717-105">구문</span><span class="sxs-lookup"><span data-stu-id="6f717-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f717-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f717-106">Parameters</span></span>  

 `cSearchInfo`  
 <span data-ttu-id="6f717-107">진행 `ULONG32` 의 크기를 나타내는입니다 `rgpSearchInfo` .</span><span class="sxs-lookup"><span data-stu-id="6f717-107">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="6f717-108">제한이 `ULONG32` 검색 정보를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="6f717-109">제한이 반환 된 [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-109">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f717-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="6f717-110">Return Value</span></span>  

 <span data-ttu-id="6f717-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f717-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f717-112">Requirements</span></span>  

 <span data-ttu-id="6f717-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6f717-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f717-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f717-114">See also</span></span>

- [<span data-ttu-id="6f717-115">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f717-115">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
