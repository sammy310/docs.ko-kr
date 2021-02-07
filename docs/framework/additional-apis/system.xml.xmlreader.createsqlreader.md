---
description: '자세히 알아보기: CreateSqlReader 메서드'
title: CreateSqlReader 메서드 (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 61d594c0438c86863ce4052387439f5483d8a34c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740436"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="a00b6-103">XmlReader.CreateSqlReader 메서드</span><span class="sxs-lookup"><span data-stu-id="a00b6-103">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="a00b6-104">구문 분석을 위해 지정한 스트림, 설정 및 컨텍스트 정보를 사용하여 새 <xref:System.Xml.XmlReader> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-104">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="a00b6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a00b6-105">Parameters</span></span>

- <span data-ttu-id="a00b6-106">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="a00b6-106">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="a00b6-107">XML 데이터가 포함된 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-107">The stream that contains the XML data.</span></span>

- <span data-ttu-id="a00b6-108">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="a00b6-108">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="a00b6-109">새 <xref:System.Xml.XmlReader> 인스턴스의 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-109">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="a00b6-110">이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-110">This value can be `null`.</span></span>

- <span data-ttu-id="a00b6-111">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="a00b6-111">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="a00b6-112">XML 조각을 구문 분석하는 데 필요한 컨텍스트 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-112">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="a00b6-113">이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-113">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="a00b6-114">반환</span><span class="sxs-lookup"><span data-stu-id="a00b6-114">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="a00b6-115">스트림의 XML 데이터를 읽는 데 사용되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-115">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="a00b6-116">설명</span><span class="sxs-lookup"><span data-stu-id="a00b6-116">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a00b6-117">`XmlReader.CreateSqlReader`메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-117">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a00b6-118">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-118">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a00b6-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a00b6-119">Requirements</span></span>

<span data-ttu-id="a00b6-120">**네임스페이스:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="a00b6-120">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="a00b6-121">**어셈블리:** System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="a00b6-121">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="a00b6-122">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00b6-122">**.NET Framework versions:** Available since 2.0.</span></span>
