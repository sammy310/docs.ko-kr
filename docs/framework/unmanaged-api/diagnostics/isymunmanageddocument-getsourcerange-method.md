---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetSourceRange 메서드'
title: ISymUnmanagedDocument::GetSourceRange 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: 98718298d7bf2f44d418a40f17ad19cdee0b6771
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790167"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="35cae-103">ISymUnmanagedDocument::GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="35cae-103">ISymUnmanagedDocument::GetSourceRange Method</span></span>

<span data-ttu-id="35cae-104">포함 된 소스의 지정 된 범위를 지정 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-104">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="35cae-105">버퍼는 원본을 저장할 수 있을 만큼 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-105">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35cae-106">구문</span><span class="sxs-lookup"><span data-stu-id="35cae-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35cae-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35cae-107">Parameters</span></span>  

 `startLine`  
 <span data-ttu-id="35cae-108">진행 현재 문서의 시작 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-108">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="35cae-109">진행 현재 문서의 시작 열입니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-109">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="35cae-110">진행 현재 문서의 마지막 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-110">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="35cae-111">진행 현재 문서의 마지막 열입니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-111">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="35cae-112">진행 소스의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-112">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="35cae-113">제한이 원본 크기를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-113">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="35cae-114">제한이 지정 된 소스 문서 범위의 크기와 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-114">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35cae-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="35cae-115">Return Value</span></span>  

 <span data-ttu-id="35cae-116">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="35cae-116">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35cae-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35cae-117">See also</span></span>

- [<span data-ttu-id="35cae-118">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35cae-118">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
