---
description: '자세히 알아보기: GetScope2 메서드'
title: GetScope2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: 9a68f02a638b58e7a70207d8610607bf24b2b96b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718345"
---
# <a name="getscope2-method"></a><span data-ttu-id="20dde-103">GetScope2 메서드</span><span class="sxs-lookup"><span data-stu-id="20dde-103">GetScope2 Method</span></span>

<span data-ttu-id="20dde-104">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20dde-104">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20dde-105">구문</span><span class="sxs-lookup"><span data-stu-id="20dde-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="20dde-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20dde-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="20dde-107">대상 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20dde-107">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="20dde-108">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20dde-108">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="20dde-109">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="20dde-109">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="20dde-110">표시 된 범위에 대 한 [IMetaDataImport2 interface](../metadata/imetadataimport2-interface.md) 인터페이스에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="20dde-110">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20dde-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="20dde-111">Return Value</span></span>  

 <span data-ttu-id="20dde-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20dde-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20dde-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20dde-113">Requirements</span></span>  

 <span data-ttu-id="20dde-114">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="20dde-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20dde-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20dde-115">See also</span></span>

- [<span data-ttu-id="20dde-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20dde-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="20dde-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20dde-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="20dde-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="20dde-118">ALink API</span></span>](index.md)
