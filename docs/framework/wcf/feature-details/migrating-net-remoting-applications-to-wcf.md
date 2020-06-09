---
title: .NET Remoting 애플리케이션을 WCF로 마이그레이션
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: d12583904e4a025a8de1103f0fb48f4656d6855e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598777"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>.NET Remoting 애플리케이션을 WCF로 마이그레이션
**이 항목은 이전 버전의 기존 응용 프로그램과의 호환성을 위해 유지 되며 새로운 개발에는 권장 되지 않는 레거시 기술과 관련 되어 있습니다. 이제 WCF를 사용 하 여 배포 응용 프로그램을 개발 해야 합니다.**  
  
 기존 .NET Remoting 응용 프로그램에서 WCF를 활용 하는 방법에는 두 가지가 있습니다. 통합 및 마이그레이션. 통합을 사용 하면 .NET Remoting 2.0 및 WCF를 함께 실행 하 여 기존 .NET Remoting 2.0 코드를 수정 하지 않고도 두 기술 모두에 동일한 비즈니스 개체를 동시에 노출할 수 있습니다. 통합 하려면 .NET Framework 2.0 이상에서 실행 해야 합니다. WCF 기능을 활용 하려는 데 Remoting 2.0 시스템과의 유선 호환성이 필요 하지 않은 경우 전체 서비스를 WCF로 마이그레이션할 수 있습니다. .NET Remoting 2.0에서 WCF로 마이그레이션하려면 원격 개체의 인터페이스 및 해당 구성 설정을 변경 해야 합니다. 이러한 항목은 모두 [원격에서 Windows Communication Foundation로](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80))설명 됩니다.  
  
## <a name="see-also"></a>참고 항목

- [개념적 개요](../conceptual-overview.md)
