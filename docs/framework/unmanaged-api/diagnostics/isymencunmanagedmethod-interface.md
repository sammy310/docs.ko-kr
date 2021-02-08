---
description: '자세히 알아보기: ISymENCUnmanagedMethod 인터페이스'
title: ISymENCUnmanagedMethod 인터페이스
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 59dd56c20279b2507fc4432182d0abb5b3e9c289
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790323"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="93aa9-103">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93aa9-103">ISymENCUnmanagedMethod Interface</span></span>

<span data-ttu-id="93aa9-104">편집 하며 계속 하기 기능에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93aa9-104">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93aa9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="93aa9-105">Methods</span></span>  
  
|<span data-ttu-id="93aa9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="93aa9-106">Method</span></span>|<span data-ttu-id="93aa9-107">설명</span><span class="sxs-lookup"><span data-stu-id="93aa9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93aa9-108">GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="93aa9-108">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="93aa9-109">이 메서드에 줄이 있는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93aa9-109">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="93aa9-110">GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="93aa9-110">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="93aa9-111">이 메서드에 줄이 있는 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93aa9-111">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="93aa9-112">GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="93aa9-112">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="93aa9-113">오프셋과 연결 된 줄의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93aa9-113">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="93aa9-114">GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="93aa9-114">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="93aa9-115">오프셋과 연결 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93aa9-115">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="93aa9-116">GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="93aa9-116">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="93aa9-117">특정 문서에서 메서드의 가장 작은 시작 줄과 가장 큰 끝 줄을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93aa9-117">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93aa9-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93aa9-118">Requirements</span></span>  

 <span data-ttu-id="93aa9-119">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="93aa9-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93aa9-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93aa9-120">See also</span></span>

- [<span data-ttu-id="93aa9-121">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93aa9-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
