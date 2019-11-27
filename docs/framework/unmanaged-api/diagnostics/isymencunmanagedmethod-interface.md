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
ms.openlocfilehash: 47477bb473df8b568844d07bea704df681c9b95d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448599"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="896c0-102">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="896c0-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="896c0-103">편집 하며 계속 하기 기능에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="896c0-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="896c0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="896c0-104">Methods</span></span>  
  
|<span data-ttu-id="896c0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="896c0-105">Method</span></span>|<span data-ttu-id="896c0-106">설명</span><span class="sxs-lookup"><span data-stu-id="896c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="896c0-107">GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="896c0-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="896c0-108">이 메서드에 줄이 있는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="896c0-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="896c0-109">GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="896c0-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="896c0-110">이 메서드에 줄이 있는 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="896c0-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="896c0-111">GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="896c0-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="896c0-112">오프셋과 연결 된 줄의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="896c0-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="896c0-113">GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="896c0-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="896c0-114">오프셋과 연결 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="896c0-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="896c0-115">GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="896c0-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="896c0-116">특정 문서에서 메서드의 가장 작은 시작 줄과 가장 큰 끝 줄을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="896c0-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="896c0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="896c0-117">Requirements</span></span>  
 <span data-ttu-id="896c0-118">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="896c0-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896c0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="896c0-119">See also</span></span>

- [<span data-ttu-id="896c0-120">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="896c0-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
