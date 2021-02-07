---
description: '자세히 알아보기: ISymUnmanagedReader:: Initialize 메서드'
title: ISymUnmanagedReader::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
ms.openlocfilehash: cf7f5df3efed7823fc36bd6c9fc56e0c49d17443
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763880"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="8a1f9-103">ISymUnmanagedReader::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="8a1f9-103">ISymUnmanagedReader::Initialize Method</span></span>

<span data-ttu-id="8a1f9-104">이 판독기가 연결 될 메타 데이터 가져오기 인터페이스를 사용 하 여 기호 판독기를 모듈의 파일 이름과 함께 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-104">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a1f9-105">이 메서드는 한 번만 호출할 수 있으며 다른 판독기 메서드 보다 먼저 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-105">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a1f9-106">구문</span><span class="sxs-lookup"><span data-stu-id="8a1f9-106">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a1f9-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a1f9-107">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="8a1f9-108">진행 이 판독기가 연결 되는 메타 데이터 가져오기 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-108">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="8a1f9-109">진행 모듈의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-109">[in] The file name of the module.</span></span> <span data-ttu-id="8a1f9-110">대신 매개 변수를 사용할 수 있습니다 `pIStream` .</span><span class="sxs-lookup"><span data-stu-id="8a1f9-110">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="8a1f9-111">진행 검색할 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-111">[in] The path to search.</span></span> <span data-ttu-id="8a1f9-112">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-112">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="8a1f9-113">진행 Filename 매개 변수의 대 안으로 사용 되는 파일 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-113">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a1f9-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="8a1f9-114">Return Value</span></span>  

 <span data-ttu-id="8a1f9-115">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a1f9-116">설명</span><span class="sxs-lookup"><span data-stu-id="8a1f9-116">Remarks</span></span>  

 <span data-ttu-id="8a1f9-117">또는 매개 변수 중 하나만 지정 해야 `filename` `pIStream` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-117">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="8a1f9-118">`searchPath` 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1f9-118">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a1f9-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a1f9-119">Requirements</span></span>  

 <span data-ttu-id="8a1f9-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8a1f9-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1f9-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a1f9-121">See also</span></span>

- [<span data-ttu-id="8a1f9-122">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a1f9-122">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
