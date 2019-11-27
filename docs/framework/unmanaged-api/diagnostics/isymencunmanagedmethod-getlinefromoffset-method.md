---
title: ISymENCUnmanagedMethod::GetLineFromOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 94a571a4bc01b805387aebe5a6e23bad0b735313
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448643"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="68c4a-102">ISymENCUnmanagedMethod::GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="68c4a-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="68c4a-103">오프셋과 연결 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="68c4a-104">Offset 매개 변수 (`dwOffset`)가 시퀀스 위치가 아니면이 메서드는 이전 오프셋과 관련 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c4a-105">구문</span><span class="sxs-lookup"><span data-stu-id="68c4a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68c4a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68c4a-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="68c4a-107">진행 오프셋을 포함 하는 `ULONG32`입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="68c4a-108">제한이 줄을 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="68c4a-109">제한이 열을 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="68c4a-110">제한이 끝 줄을 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="68c4a-111">제한이 끝 열을 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="68c4a-112">제한이 연결 된 시퀀스 위치를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68c4a-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="68c4a-113">Return Value</span></span>  
 <span data-ttu-id="68c4a-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4a-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68c4a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68c4a-115">Requirements</span></span>  
 <span data-ttu-id="68c4a-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="68c4a-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68c4a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68c4a-117">See also</span></span>

- [<span data-ttu-id="68c4a-118">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68c4a-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
