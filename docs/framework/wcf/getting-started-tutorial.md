---
title: '자습서: Windows 통신 기반 응용 프로그램 시작'
description: 이 자습서에서는 WCF 응용 프로그램을 만들기 위한 소개를 제공합니다.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184119"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>자습서: Windows 통신 기반 응용 프로그램 시작
다음 자습서 시리즈에서는 WCF(Windows 통신 재단) 프로그래밍 환경을 소개합니다. 이 자습서를 순서대로 진행하면 WCF 응용 프로그램을 만드는 데 필요한 단계를 소개해 드립니다. 완료되면 실행 중인 WCF 서비스와 서비스를 호출하는 WCF 클라이언트가 표시됩니다.

이 자습서에서는 Visual Studio를 개발 환경으로 사용하고 있다고 가정합니다. 다른 개발 환경을 사용하는 경우 Visual Studio 관련 지침을 무시합니다.

다운로드하여 실행할 수 있는 샘플 WCF 응용 프로그램에 대한 Windows [통신 재단 샘플을](samples/index.md)참조하십시오. 샘플에 대한 소개는 [시작 샘플 을](samples/getting-started-sample.md)참조하십시오.

서비스 및 클라이언트 만들기에 대한 자세한 내용은 [기본 WCF 프로그래밍](basic-wcf-programming.md)을 참조하십시오.

## <a name="wcf-tutorials"></a>WCF 자습서

처음 세 가지 자습서에서는 WCF 서비스 계약을 정의하는 방법, 이를 구현하는 방법 및 이를 호스트하는 방법을 설명합니다. 사용자가 만드는 서비스는 콘솔 응용 프로그램 내에서 자체 호스팅됩니다. 또한 IIS(Microsoft 인터넷 정보 서비스)에서 서비스를 호스팅할 수도 있습니다. 자세한 내용은 [IIS에서 WCF 서비스를 호스팅하는 방법을](feature-details/how-to-host-a-wcf-service-in-iis.md)참조하십시오. 코드를 사용하여 자습서에서 서비스를 구성하지만 [구성 파일 내에서 서비스를 구성할](configuring-services-using-configuration-files.md)수도 있습니다.

- [자습서: 서비스 계약 정의](how-to-define-a-wcf-service-contract.md)

    사용자 정의 인터페이스를 사용하여 WCF 계약을 만듭니다. 이 계약은 서비스가 노출하는 기능을 정의합니다.

- [자습서: 서비스 계약 구현](how-to-implement-a-wcf-contract.md)

    계약을 정의한 후에는 서비스 클래스로 계약을 구현해야 합니다.

- [자습서: 기본 서비스 호스트 및 실행](how-to-host-and-run-a-basic-wcf-service.md)

    서비스에 대한 엔드포인트를 구성하고 콘솔 응용 프로그램에서 서비스를 호스트합니다. 서비스가 활성화되려면 서비스를 구성하고 런타임 환경 내에서 호스트해야 합니다. 이 런타임 환경은 서비스를 만들고 해당 컨텍스트 및 수명을 제어합니다.

다음 두 자습서에서는 클라이언트 응용 프로그램을 만들고 구성하고 사용하여 서비스가 노출하는 작업을 호출하는 방법을 설명합니다. 서비스는 클라이언트 애플리케이션이 서비스와 통신하는 데 필요한 정보를 정의하는 메타데이터를 게시합니다. Visual Studio는 이 메타데이터에 액세스하는 프로세스를 자동화하고 이를 사용하여 서비스에 대한 클라이언트 응용 프로그램을 구성합니다. Visual Studio를 사용하지 않기로 결정한 경우 [서비스모델 메타데이터 유틸리티*도구(Svcutil.exe)를*](servicemodel-metadata-utility-tool-svcutil-exe.md) 대신 사용할 수 있습니다.

- [자습서: 클라이언트 만들기](how-to-create-a-wcf-client.md)

    WCF 서비스에서 WCF 클라이언트 프록시를 만들기 위해 메타데이터를 검색합니다. Visual Studio를 사용하여 서비스 참조를 추가하거나 ServiceModel 메타데이터 유틸리티 도구를 사용하여 메타데이터를 검색할 수 있습니다. 클라이언트가 서비스에 액세스하는 데 사용하는 끝점을 지정합니다.

- [자습서: 클라이언트 사용](how-to-use-a-wcf-client.md)

    WCF 클라이언트 프록시를 사용하여 서비스 작업을 호출합니다.

## <a name="reference"></a>참조

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>참고 항목

- [개념적 개요](conceptual-overview.md)
- [문서 가이드](guide-to-the-documentation.md)
- [윈도우 커뮤니케이션 재단이란?](whats-wcf.md)
- [WCF 기능 세부 정보](feature-details/index.md)
- [기본 프로그래밍 수명 주기](basic-programming-lifecycle.md)
- [클라이언트 구축](building-clients.md)
- [기본 WCF 프로그래밍](basic-wcf-programming.md)
- [방법: 이중 계약 만들기](feature-details/how-to-create-a-duplex-contract.md)
- [방법: 이중 계약을 통해 서비스에 액세스](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [서비스 모델 메타 데이터 유틸리티 도구 (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [방법: Svcutil.exe를 사용하여 메타데이터 문서를 다운로드합니다.](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [방법: 구성 파일을 사용하여 서비스에 대한 메타데이터 게시](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](using-bindings-to-configure-services-and-clients.md)
- [시작 샘플](samples/getting-started-sample.md)
- [윈도우 커뮤니케이션 재단 샘플](samples/index.md)
- [자체 호스팅](samples/self-host.md)
