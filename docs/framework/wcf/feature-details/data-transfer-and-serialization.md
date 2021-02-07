---
description: 데이터 전송 및 Serialization에 대해 자세히 알아보세요.
title: 데이터 전송 및 Serialization
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 50e5068efc10d706fb9ce2634998408e48037ded
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756567"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="a15da-103">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="a15da-103">Data Transfer and Serialization</span></span>

<span data-ttu-id="a15da-104">연결된 시스템에서 서비스 및 클라이언트는 데이터 교환에 의존하여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-104">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="a15da-105">서비스 또는 클라이언트 개발자는 효율적이 고 쉽게 관리할 수 있는 응용 프로그램을 만들기 위해 WCF (Windows Communication Foundation)에서 데이터 및 데이터 serialization을 처리 하는 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-105">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a15da-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a15da-106">In This Section</span></span>  

 [<span data-ttu-id="a15da-107">서비스 계약에서 데이터 전송 지정</span><span class="sxs-lookup"><span data-stu-id="a15da-107">Specifying Data Transfer in Service Contracts</span></span>](specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="a15da-108">서비스에서 데이터 전송의 기본 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-108">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="a15da-109">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="a15da-109">Using Data Contracts</span></span>](using-data-contracts.md)  
 <span data-ttu-id="a15da-110">데이터 계약의 정의와 데이터 계약을 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-110">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="a15da-111">데이터 계약 직렬 변환기</span><span class="sxs-lookup"><span data-stu-id="a15da-111">Data Contract Serializer</span></span>](data-contract-serializer.md)  
 <span data-ttu-id="a15da-112"><xref:System.Runtime.Serialization.DataContractSerializer> 클래스 또는 <xref:System.Runtime.Serialization.XmlObjectSerializer> 클래스의 확장을 사용하여 데이터의 serialization을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-112">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="a15da-113">XmlSerializer 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="a15da-113">Using the XmlSerializer Class</span></span>](using-the-xmlserializer-class.md)  
 <span data-ttu-id="a15da-114"><xref:System.Xml.Serialization.XmlSerializer> 클래스 대신 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스를 사용하는 방법 및 이유에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-114">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="a15da-115">메시지 계약 사용</span><span class="sxs-lookup"><span data-stu-id="a15da-115">Using Message Contracts</span></span>](using-message-contracts.md)  
 <span data-ttu-id="a15da-116">메시지 계약에서 SOAP 메시지를 정밀하게 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-116">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="a15da-117">Message 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="a15da-117">Using the Message Class</span></span>](using-the-message-class.md)  
 <span data-ttu-id="a15da-118">Message 클래스 기능을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-118">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="a15da-119">필터링</span><span class="sxs-lookup"><span data-stu-id="a15da-119">Filtering</span></span>](filtering.md)  
 <span data-ttu-id="a15da-120">여러 조건을 기반으로 메시지 전처리를 사용하는 필터링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-120">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="a15da-121">큰 데이터 및 스트리밍</span><span class="sxs-lookup"><span data-stu-id="a15da-121">Large Data and Streaming</span></span>](large-data-and-streaming.md)  
 <span data-ttu-id="a15da-122">이진 파일과 같은 큰 데이터 블록을 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-122">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="a15da-123">데이터에 대한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="a15da-123">Security Considerations for Data</span></span>](security-considerations-for-data.md)  
 <span data-ttu-id="a15da-124">데이터 전송 및 serialization을 프로그래밍할 때 알고 있어야 하는 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-124">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="a15da-125">데이터 전송 아키텍처 개요</span><span class="sxs-lookup"><span data-stu-id="a15da-125">Data Transfer Architectural Overview</span></span>](data-transfer-architectural-overview.md)  
 <span data-ttu-id="a15da-126">WCF의 전체 데이터 전송 디자인에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a15da-126">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a15da-127">참고</span><span class="sxs-lookup"><span data-stu-id="a15da-127">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="a15da-128">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a15da-128">Related Sections</span></span>  

 [<span data-ttu-id="a15da-129">인코더 및 Serializer 확장</span><span class="sxs-lookup"><span data-stu-id="a15da-129">Extending Encoders and Serializers</span></span>](../extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="a15da-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a15da-130">See also</span></span>

- [<span data-ttu-id="a15da-131">모범 사례: 데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="a15da-131">Best Practices: Data Contract Versioning</span></span>](../best-practices-data-contract-versioning.md)
- [<span data-ttu-id="a15da-132">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="a15da-132">Service Versioning</span></span>](../service-versioning.md)
