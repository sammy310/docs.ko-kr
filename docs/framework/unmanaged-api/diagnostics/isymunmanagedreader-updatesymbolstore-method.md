---
description: '자세히 알아보기: ISymUnmanagedReader:: UpdateSymbolStore 메서드'
title: ISymUnmanagedReader::UpdateSymbolStore 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: eb6ca01b7978b66d0a8674e5b83ce26ee341e890
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763750"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="63920-103">ISymUnmanagedReader::UpdateSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="63920-103">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>

<span data-ttu-id="63920-104">기존 기호 저장소를 델타 기호 저장소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="63920-104">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="63920-105">이 메서드는 편집 하며 계속 하기 시나리오에서 델타를 원래 PE (이식 가능한 실행) 파일에 일치 하도록 기호 저장소를 업데이트 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63920-105">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63920-106">또는 매개 변수 중 하나만 지정 해야 `filename` `pIStream` 합니다.</span><span class="sxs-lookup"><span data-stu-id="63920-106">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="63920-107">을 `filename` 지정 하면 기호 저장소가 해당 파일의 기호를 사용 하 여 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63920-107">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="63920-108">을 `pIStream` 지정 하면 저장소는의 데이터로 업데이트 됩니다 <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="63920-108">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63920-109">구문</span><span class="sxs-lookup"><span data-stu-id="63920-109">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63920-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63920-110">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="63920-111">진행 기호 저장소를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63920-111">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="63920-112">진행 매개 변수의 대 안으로 사용 되는 파일 스트림입니다 `filename` .</span><span class="sxs-lookup"><span data-stu-id="63920-112">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63920-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="63920-113">Return Value</span></span>  

 <span data-ttu-id="63920-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="63920-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63920-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63920-115">Requirements</span></span>  

 <span data-ttu-id="63920-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="63920-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63920-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63920-117">See also</span></span>

- [<span data-ttu-id="63920-118">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63920-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
