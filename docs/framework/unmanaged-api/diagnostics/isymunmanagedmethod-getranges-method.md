---
title: ISymUnmanagedMethod::GetRanges 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ca1db2bf85f42117f686a8cb483907003927c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205851"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="1a20c-102">ISymUnmanagedMethod::GetRanges 메서드</span><span class="sxs-lookup"><span data-stu-id="1a20c-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="1a20c-103">문서의 위치를 지정 된 MSIL (Microsoft intermediate language)이이 메서드 내에서 위치를 포함 하는 범위에 해당 하는 시작 및 종료 오프셋된 쌍의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="1a20c-104">정수 배열이 배열과 [시작, 종료, 시작, 종료] 형식은입니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="1a20c-105">범위 쌍의 개수는 2로 나눈 결과 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a20c-106">구문</span><span class="sxs-lookup"><span data-stu-id="1a20c-106">Syntax</span></span>  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a20c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a20c-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="1a20c-108">[in] 오프셋이 요청 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="1a20c-109">[in] 범위에 해당 하는 문서 줄.</span><span class="sxs-lookup"><span data-stu-id="1a20c-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="1a20c-110">[in] 범위에 해당 하는 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="1a20c-111">[in] `ranges` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="1a20c-112">[out] 에 대 한 포인터를 `ULONG32` 범위를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="1a20c-113">[out] 범위를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a20c-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="1a20c-114">Return Value</span></span>  
 <span data-ttu-id="1a20c-115">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1a20c-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a20c-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a20c-116">Requirements</span></span>  
 <span data-ttu-id="1a20c-117">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a20c-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a20c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a20c-118">See also</span></span>

- [<span data-ttu-id="1a20c-119">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a20c-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
