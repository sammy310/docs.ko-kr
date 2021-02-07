---
description: '자세히 알아보기: WriteStartHeaders 메서드'
title: WriteStartHeaders 메서드 (System.servicemodel)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 20cadf5f1eecf6d8e02c5dc4597889abaef4ec36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699365"
---
# <a name="messagewritestartheaders-method"></a><span data-ttu-id="a1af3-103">WriteStartHeaders 메서드</span><span class="sxs-lookup"><span data-stu-id="a1af3-103">Message.WriteStartHeaders Method</span></span>

<span data-ttu-id="a1af3-104">메서드를 호출 하 여 시작 헤더를 XML 파일에 씁니다 <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a1af3-104">Writes the start header into an XML file by calling the <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a><span data-ttu-id="a1af3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1af3-105">Parameters</span></span>

- <span data-ttu-id="a1af3-106">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="a1af3-106">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="a1af3-107">시작 헤더를 XML 파일에 쓰는 데 사용 되는 작성기입니다.</span><span class="sxs-lookup"><span data-stu-id="a1af3-107">The writer that is used to write the start header into an XML file.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1af3-108">설명</span><span class="sxs-lookup"><span data-stu-id="a1af3-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a1af3-109">`Message.WriteStartHeaders`메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1af3-109">The `Message.WriteStartHeaders` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a1af3-110">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1af3-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1af3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1af3-111">Requirements</span></span>

<span data-ttu-id="a1af3-112">**네임스페이스:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="a1af3-112">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="a1af3-113">**어셈블리:** System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="a1af3-113">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="a1af3-114">**.NET Framework 버전:** 3.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1af3-114">**.NET Framework versions:** Available since 3.0.</span></span>
