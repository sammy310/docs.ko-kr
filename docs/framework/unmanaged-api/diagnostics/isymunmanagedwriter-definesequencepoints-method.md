---
description: ISymUnmanagedWriter::D efineSequencePoints 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedWriter::DefineSequencePoints 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
ms.openlocfilehash: 0c5ac9854ef341512f58cb1cd63ed7dfcde9962e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762333"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="5214e-103">ISymUnmanagedWriter::DefineSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="5214e-103">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>

<span data-ttu-id="5214e-104">현재 메서드 내에서 시퀀스 위치 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-104">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="5214e-105">각 시작 줄과 시작 열은 메서드 내에서 문의 시작을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-105">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="5214e-106">각 끝 줄과 끝 열은 메서드 내에서 문의 끝을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-106">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="5214e-107">배열은 오프셋의 오름차순으로 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-107">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="5214e-108">오프셋은 항상 메서드의 시작 부분에서 바이트 단위로 측정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-108">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5214e-109">구문</span><span class="sxs-lookup"><span data-stu-id="5214e-109">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5214e-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5214e-110">Parameters</span></span>  

 `document`  
 <span data-ttu-id="5214e-111">진행 시퀀스 위치를 정의할 문서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-111">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="5214e-112">진행 `ULONG32` 각 `offsets` ,, `lines` `columns` , `endLines` 및 `endColumns` 버퍼의 크기를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-112">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="5214e-113">진행 메서드의 시작 부분에서 측정 한 시퀀스 위치의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-113">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="5214e-114">진행 시퀀스 위치의 시작 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-114">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="5214e-115">진행 시퀀스 위치의 시작 열 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-115">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="5214e-116">진행 시퀀스 위치의 끝 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-116">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="5214e-117">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-117">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="5214e-118">진행 시퀀스 위치의 끝 열 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-118">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="5214e-119">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-119">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5214e-120">Return Value</span><span class="sxs-lookup"><span data-stu-id="5214e-120">Return Value</span></span>  

 <span data-ttu-id="5214e-121">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5214e-121">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5214e-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5214e-122">Requirements</span></span>  

 <span data-ttu-id="5214e-123">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5214e-123">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5214e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5214e-124">See also</span></span>

- [<span data-ttu-id="5214e-125">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5214e-125">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
