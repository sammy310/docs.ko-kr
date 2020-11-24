---
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
ms.openlocfilehash: 6670d985eed4c55550b23d3f4110ee20f3b75661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675830"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="afbac-102">ISymUnmanagedReader::UpdateSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="afbac-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>

<span data-ttu-id="afbac-103">기존 기호 저장소를 델타 기호 저장소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="afbac-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="afbac-104">이 메서드는 편집 하며 계속 하기 시나리오에서 델타를 원래 PE (이식 가능한 실행) 파일에 일치 하도록 기호 저장소를 업데이트 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afbac-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afbac-105">또는 매개 변수 중 하나만 지정 해야 `filename` `pIStream` 합니다.</span><span class="sxs-lookup"><span data-stu-id="afbac-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="afbac-106">을 `filename` 지정 하면 기호 저장소가 해당 파일의 기호를 사용 하 여 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afbac-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="afbac-107">을 `pIStream` 지정 하면 저장소는의 데이터로 업데이트 됩니다 <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="afbac-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afbac-108">구문</span><span class="sxs-lookup"><span data-stu-id="afbac-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afbac-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="afbac-109">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="afbac-110">진행 기호 저장소를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="afbac-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="afbac-111">진행 매개 변수의 대 안으로 사용 되는 파일 스트림입니다 `filename` .</span><span class="sxs-lookup"><span data-stu-id="afbac-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afbac-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="afbac-112">Return Value</span></span>  

 <span data-ttu-id="afbac-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="afbac-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afbac-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="afbac-114">Requirements</span></span>  

 <span data-ttu-id="afbac-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="afbac-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afbac-116">참조</span><span class="sxs-lookup"><span data-stu-id="afbac-116">See also</span></span>

- [<span data-ttu-id="afbac-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="afbac-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
