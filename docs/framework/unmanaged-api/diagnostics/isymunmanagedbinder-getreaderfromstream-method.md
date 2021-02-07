---
description: '자세히 알아보기: ISymUnmanagedBinder:: GetReaderFromStream 메서드'
title: ISymUnmanagedBinder::GetReaderFromStream 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
ms.openlocfilehash: da238ed8e450250be427ae27c4492c1e091f7997
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689991"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="70b80-103">ISymUnmanagedBinder::GetReaderFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="70b80-103">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>

<span data-ttu-id="70b80-104">메타 데이터 인터페이스 및 기호 저장소를 포함 하는 스트림이 지정 된 경우 지정 된 기호 저장소에서 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b80-104">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70b80-105">구문</span><span class="sxs-lookup"><span data-stu-id="70b80-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70b80-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70b80-106">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="70b80-107">진행 메타 데이터 가져오기 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70b80-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="70b80-108">진행 기호 저장소를 포함 하는 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70b80-108">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="70b80-109">제한이 반환 된 [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70b80-109">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70b80-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="70b80-110">Return Value</span></span>  

 <span data-ttu-id="70b80-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="70b80-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70b80-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70b80-112">Requirements</span></span>  

 <span data-ttu-id="70b80-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="70b80-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b80-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70b80-114">See also</span></span>

- [<span data-ttu-id="70b80-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70b80-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
