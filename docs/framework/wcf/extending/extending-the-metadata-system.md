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
# <a name="extending-the-metadata-system"></a>메타데이터 시스템 확장

WCF (Windows Communication Foundation) 메타 데이터 시스템은 서비스 기반 응용 프로그램을 구현 하는 데 필요한 메타 데이터를 나타내는 클래스 및 인터페이스의 그룹입니다. 클래스를 수정 또는 확장하거나 인터페이스를 구현 및 구성하여 WSDL(웹 서비스 기술 언어) 확장이나 사용자 지정 WS-PolicyAttachments 어설션 같은 사용자 지정 메타데이터를 내보내고 가져옵니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [WCF 확장에 대한 사용자 지정 메타데이터 내보내기](exporting-custom-metadata-for-a-wcf-extension.md)  
 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 인터페이스를 구현 및 사용하여 사용자 지정 정책 어설션을 WSDL 문서에 포함하는 방법에 대해 설명합니다.  
  
 [WCF 확장에 대한 사용자 지정 메타데이터 가져오기](importing-custom-metadata-for-a-wcf-extension.md)  
 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 인터페이스를 구현 및 사용하여 WSDL 문서의 사용자 지정 정책 어설션을 읽고 응답하는 방법에 대해 설명합니다.  
  
 [사용자 지정 바인딩을 통해 메타데이터 게시 및 검색](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 사용자 지정 바인딩을 통해 메타데이터를 교환하는 방법에 대해 설명합니다.
