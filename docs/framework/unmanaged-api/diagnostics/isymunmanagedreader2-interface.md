---
description: '자세히 알아보기: ISymUnmanagedReader2 인터페이스'
title: ISymUnmanagedReader2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: 2e6d994a3252b7fb09b2915266e3142255878a88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763620"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="d0122-103">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0122-103">ISymUnmanagedReader2 Interface</span></span>

<span data-ttu-id="d0122-104">기호 저장소 내의 문서, 메서드 및 변수에 대한 액세스를 제공하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0122-104">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="d0122-105">이 인터페이스는 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0122-105">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0122-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d0122-106">Methods</span></span>  
  
|<span data-ttu-id="d0122-107">메서드</span><span class="sxs-lookup"><span data-stu-id="d0122-107">Method</span></span>|<span data-ttu-id="d0122-108">설명</span><span class="sxs-lookup"><span data-stu-id="d0122-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0122-109">GetMethodByVersionPreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="d0122-109">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="d0122-110">메서드 토큰과 편집 하며 계속 하기 버전 번호가 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0122-110">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="d0122-111">GetMethodsInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="d0122-111">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="d0122-112">제공 된 문서에서 줄 정보를 포함 하는 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0122-112">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="d0122-113">GetSymAttributePreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="d0122-113">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="d0122-114">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0122-114">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0122-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0122-115">Requirements</span></span>  

 <span data-ttu-id="d0122-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d0122-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0122-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0122-117">See also</span></span>

- [<span data-ttu-id="d0122-118">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0122-118">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d0122-119">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0122-119">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
