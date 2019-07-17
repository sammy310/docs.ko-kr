---
title: '성능 최적화: 하드웨어 활용'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
ms.openlocfilehash: 13812fa5429bbe33341e51e4b3be14fbbcb361cb
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238446"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>성능 최적화: 하드웨어 활용
내부 아키텍처 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 두 렌더링 파이프라인, 하드웨어 및 소프트웨어를 포함 합니다. 이 항목에서는 응용 프로그램의 성능 최적화에 대 한 결정을 내릴 수 있도록 이러한 렌더링 파이프라인에 대 한 정보를 제공 합니다.  
  
## <a name="hardware-rendering-pipeline"></a>하드웨어 렌더링 파이프라인  
 결정 하는 데 가장 중요 한 요인 중 하나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 성능은 렌더링 범위는-픽셀 수가 클수록 성능 비용이 렌더링 해야 합니다. 그러나에 렌더링 하는 자세한 정보를 오프 로드할 수는 [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)]얻을 수 있는 성능 이점이 더, 합니다. 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 하드웨어 렌더링 파이프라인 활용 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 최소를 지 원하는 하드웨어 기능 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 버전 7.0입니다. 추가 최적화를 지 원하는 하드웨어에서 얻을 수 있습니다 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] PixelShader 2.0 + 기능과 버전 7.0입니다.  
  
## <a name="software-rendering-pipeline"></a>소프트웨어 렌더링 파이프라인  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 소프트웨어 렌더링 파이프라인은 CPU 바인딩된 전적으로 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SSE 및 SSE2 명령 활용은 최적화 된을 갖춘 소프트웨어 래스터 라이저를 구현 하는 CPU에서 설정 합니다. 소프트웨어 대체 (fallback) 시간이 원활 하 게 모든 하드웨어 렌더링 파이프라인을 사용 하 여 응용 프로그램 기능을 렌더링할 수 없습니다.  
  
 가장 큰 성능 문제를 렌더링 하는 픽셀 수로 정의 되는 속도 맞게 소프트웨어 모드에서 렌더링와 관련 된 경우 발생 합니다. 소프트웨어 렌더링 모드에서 성능에 대 한 관심이 경우 픽셀을 다시 그리면 횟수를 최소화 하려고 합니다. 예를 들어 올려 약간 투명 이미지를 렌더링 한 다음, 파란색 배경의 응용 프로그램이 있는 경우 모든 응용 프로그램을 두 번 픽셀 렌더링할가 있습니다. 결과적으로, 걸립니다 두 번 파란색 배경만 했다면 보다 이미지를 사용 하 여 응용 프로그램을 렌더링 하는 데 소요 되는.  
  
### <a name="graphics-rendering-tiers"></a>그래픽 렌더링 계층  
 응용 프로그램에서 실행 되는 하드웨어 구성을 예측 하기가 매우 어려울 수 있습니다. 그러나 응용 프로그램을 원활 하 게 전환 기능 다른 하드웨어에서 실행 하는 경우 각 다른 하드웨어 구성의 활용을 취할 수 있도록 허용 하는 디자인을 고려해 야 할 수 있습니다.  
  
 이 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 런타임 시 시스템의 그래픽 기능을 확인 하는 기능을 제공 합니다. 그래픽 기능 세 개의 기능 계층을 렌더링 중 하나로 비디오 카드를 범주화 하 여 결정 됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 렌더링 기능 계층을 쿼리할 수 있는 API를 노출 합니다. 응용 프로그램 하드웨어에서 지 원하는 렌더링 계층에 따라 런타임 시 다른 코드 경로 취할 수 있습니다.  
  
 렌더링 계층 수준에 가장 큰 영향을 미치는 그래픽 하드웨어 기능은 다음과 같습니다.  
  
- **비디오 RAM** 그래픽 하드웨어의 비디오 메모리 양에 따라 그래픽을 합성하는 데 사용할 수 있는 버퍼의 크기와 수를 결정합니다.  
  
- **픽셀 셰이더** 픽셀 셰이더는 픽셀별 미치는 영향을 계산하는 그래픽 처리 함수입니다. 표시된 그래픽의 해상도에 따라 표시 프레임별로 수백만 픽셀을 처리해야 할 수도 있습니다.  
  
- **꼭짓점 셰이더** 꼭짓점 셰이더는 개체의 꼭짓점 데이터에서 수학 연산을 수행하는 그래픽 처리 함수입니다.  
  
- **여러 질감 지원** 여러 질감 지원은 3D 그래픽 개체에서 혼합 작업 중에 두 개 이상의 개별 질감을 적용할 수 있는 기능을 나타냅니다. 여러 질감 지원 정도는 그래픽 하드웨어의 여러 질감 단위 수에 따라 결정됩니다.  
  
 픽셀 셰이더, 꼭 짓 점 셰이더 및 여러 질감 기능 하는 데 특정 정의할 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 에서 다양 한 렌더링 계층을 정의 하는 데 사용 되는 버전 수준이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
 그래픽 하드웨어 기능에 따라 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션의 렌더링 기능이 결정됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시스템에서는 다음 세 개의 렌더링 계층을 정의합니다.  
  
- **렌더링 계층 0** 그래픽 하드웨어 가속이 없습니다. [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 7.0 보다 낮은 버전 수준입니다.  
  
- **렌더링 계층 1** 부분 그래픽 하드웨어 가속 됩니다. 합니다 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 7.0 보다 크거나 및 **적을수록** 버전 9.0 보다 합니다.  
  
- **렌더링 계층 2** 대부분의 그래픽 기능에서는 그래픽 하드웨어 가속을 사용합니다. [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 9.0 이상입니다.  
  
 에 대 한 자세한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링 계층을 참조 하세요 [그래픽 렌더링 계층](graphics-rendering-tiers.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [WPF 응용 프로그램 성능 최적화](optimizing-wpf-application-performance.md)
- [응용 프로그램 성능 계획](planning-for-application-performance.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
- [2차원 그래픽 및 이미징](optimizing-performance-2d-graphics-and-imaging.md)
- [개체 동작](optimizing-performance-object-behavior.md)
- [애플리케이션 리소스](optimizing-performance-application-resources.md)
- [텍스트](optimizing-performance-text.md)
- [데이터 바인딩](optimizing-performance-data-binding.md)
- [기타 성능 권장 사항](optimizing-performance-other-recommendations.md)
