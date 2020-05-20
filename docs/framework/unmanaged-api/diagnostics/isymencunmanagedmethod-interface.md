---
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
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441879"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="f4ad9-102">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4ad9-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="f4ad9-103">편집 하며 계속 하기 기능에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ad9-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4ad9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f4ad9-104">Methods</span></span>  
  
|<span data-ttu-id="f4ad9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f4ad9-105">Method</span></span>|<span data-ttu-id="f4ad9-106">설명</span><span class="sxs-lookup"><span data-stu-id="f4ad9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4ad9-107">GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="f4ad9-107">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="f4ad9-108">이 메서드에 줄이 있는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ad9-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="f4ad9-109">GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="f4ad9-109">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="f4ad9-110">이 메서드에 줄이 있는 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ad9-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="f4ad9-111">GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="f4ad9-111">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="f4ad9-112">오프셋과 연결 된 줄의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ad9-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="f4ad9-113">GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="f4ad9-113">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="f4ad9-114">오프셋과 연결 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ad9-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="f4ad9-115">GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="f4ad9-115">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="f4ad9-116">특정 문서에서 메서드의 가장 작은 시작 줄과 가장 큰 끝 줄을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ad9-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4ad9-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4ad9-117">Requirements</span></span>  
 <span data-ttu-id="f4ad9-118">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="f4ad9-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ad9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4ad9-119">See also</span></span>

- [<span data-ttu-id="f4ad9-120">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4ad9-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
