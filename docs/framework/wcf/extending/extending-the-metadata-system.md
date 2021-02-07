---
description: '자세한 정보: 메타 데이터 시스템 확장'
title: 메타데이터 시스템 확장
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: e8409e29f9dc604ccc6bf399497f3d48f3bcd8f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685558"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="e65f7-103">메타데이터 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="e65f7-103">Extending the Metadata System</span></span>

<span data-ttu-id="e65f7-104">WCF (Windows Communication Foundation) 메타 데이터 시스템은 서비스 기반 응용 프로그램을 구현 하는 데 필요한 메타 데이터를 나타내는 클래스 및 인터페이스의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="e65f7-104">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="e65f7-105">클래스를 수정 또는 확장하거나 인터페이스를 구현 및 구성하여 WSDL(웹 서비스 기술 언어) 확장이나 사용자 지정 WS-PolicyAttachments 어설션 같은 사용자 지정 메타데이터를 내보내고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e65f7-105">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e65f7-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e65f7-106">In This Section</span></span>  

 [<span data-ttu-id="e65f7-107">WCF 확장에 대한 사용자 지정 메타데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="e65f7-107">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="e65f7-108"><xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 인터페이스를 구현 및 사용하여 사용자 지정 정책 어설션을 WSDL 문서에 포함하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e65f7-108">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="e65f7-109">WCF 확장에 대한 사용자 지정 메타데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="e65f7-109">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="e65f7-110"><xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 인터페이스를 구현 및 사용하여 WSDL 문서의 사용자 지정 정책 어설션을 읽고 응답하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e65f7-110">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="e65f7-111">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="e65f7-111">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="e65f7-112">사용자 지정 바인딩을 통해 메타데이터를 교환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e65f7-112">Describes how to exchange metadata over custom bindings.</span></span>
