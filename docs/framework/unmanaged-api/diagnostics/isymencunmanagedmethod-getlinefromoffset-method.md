---
description: '자세히 알아보기: ISymENCUnmanagedMethod:: GetLineFromOffset 메서드'
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
ms.openlocfilehash: 18fe942b509340c89a4c3044e02bf8e9d952f91d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737963"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="82d75-103">ISymENCUnmanagedMethod::GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="82d75-103">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>

<span data-ttu-id="82d75-104">오프셋과 연결 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-104">Gets the line information associated with an offset.</span></span> <span data-ttu-id="82d75-105">Offset 매개 변수 ( `dwOffset` )가 시퀀스 위치가 아닌 경우이 메서드는 이전 오프셋과 관련 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-105">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82d75-106">구문</span><span class="sxs-lookup"><span data-stu-id="82d75-106">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82d75-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82d75-107">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="82d75-108">진행 `ULONG32` 오프셋을 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-108">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="82d75-109">제한이 줄을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-109">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="82d75-110">제한이 열을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-110">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="82d75-111">제한이 `ULONG32` 끝 줄을 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-111">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="82d75-112">제한이 `ULONG32` 끝 열을 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-112">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="82d75-113">제한이 연결 된 시퀀스 위치를 수신 하는에 대 한 포인터입니다 `ULONG32` .</span><span class="sxs-lookup"><span data-stu-id="82d75-113">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82d75-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="82d75-114">Return Value</span></span>  

 <span data-ttu-id="82d75-115">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="82d75-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82d75-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82d75-116">Requirements</span></span>  

 <span data-ttu-id="82d75-117">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="82d75-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d75-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82d75-118">See also</span></span>

- [<span data-ttu-id="82d75-119">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82d75-119">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
