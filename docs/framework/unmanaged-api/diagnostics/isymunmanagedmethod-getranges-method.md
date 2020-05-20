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
ms.openlocfilehash: cd5d1f2d59d3e55ba454f23d2e5dd4b1316c0df4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615178"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="7d15f-102">ISymUnmanagedMethod::GetRanges 메서드</span><span class="sxs-lookup"><span data-stu-id="7d15f-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="7d15f-103">문서에서 위치가 지정 된 경우이 메서드 내에서 위치가 포함 되는 MSIL (Microsoft 중간 언어)의 범위에 해당 하는 시작 및 종료 오프셋 쌍의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="7d15f-104">배열은 정수 배열이 며 [start, end, start, end] 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="7d15f-105">범위 쌍의 수는 배열 길이를 2로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d15f-106">구문</span><span class="sxs-lookup"><span data-stu-id="7d15f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d15f-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d15f-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="7d15f-108">진행 오프셋이 요청 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="7d15f-109">진행 범위에 해당 하는 문서 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="7d15f-110">진행 범위에 해당 하는 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="7d15f-111">[in] `ranges` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="7d15f-112">제한이 `ULONG32`범위를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="7d15f-113">제한이 범위를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d15f-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="7d15f-114">Return Value</span></span>  
 <span data-ttu-id="7d15f-115">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7d15f-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d15f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d15f-116">Requirements</span></span>  
 <span data-ttu-id="7d15f-117">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="7d15f-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d15f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d15f-118">See also</span></span>

- [<span data-ttu-id="7d15f-119">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d15f-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
