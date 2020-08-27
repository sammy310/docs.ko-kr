---
title: Model Builder에서 GPU 지원을 설치하는 방법
description: Model Builder에서 GPU 지원을 설치하는 방법을 알아봅니다.
ms.date: 08/18/2020
author: luisquintanilla
ms.author: luquinta
ms.topic: how-to
ms.openlocfilehash: ce629efa4c12a69f87196de35ebfe4331dc0800f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608555"
---
# <a name="how-to-install-gpu-support-in-model-builder"></a>Model Builder에서 GPU 지원을 설치하는 방법

Model Builder에서 GPU를 사용하기 위해 GPU 드라이버를 설치하는 방법을 알아봅니다.

## <a name="prerequisites"></a>사전 요구 사항

- Model Builder Visual Studio 확장. 이 확장은 버전 16.6.1부터 Visual Studio에 기본 제공됩니다.
- [Model Builder Visual Studio GPU 지원 확장](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).
- 하나 이상의 CUDA 호환 GPU. 호환되는 GPU 목록은 [NVIDIA 가이드](https://developer.nvidia.com/cuda-gpus)를 참조하세요.
- NVIDIA 개발자 계정. 아직 없는 경우 [체험 계정](https://developer.nvidia.com/developer-program)을 만들 수 있습니다.

## <a name="install-dependencies"></a>종속성 설치

1. [CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive)을 설치합니다. 다른 최신 버전이 아닌 CUDA v10.0을 설치해야 합니다. CUDA 버전을 여러 개 설치할 수는 없습니다.
1. [cuDNN v7.6.4 for CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download)을 설치합니다. cuDNN 버전을 여러 개 설치할 수는 없습니다. cuDNN v7.6.4 zip 파일을 다운로드하고 압축을 푼 후 `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll`을 `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`에 복사합니다.

## <a name="troubleshooting"></a>문제 해결

**어떤 GPU가 있는지 확인하려면 어떻게 해야 하나요?**

제공된 지침을 따릅니다.

1. 바탕 화면을 마우스 오른쪽 단추로 클릭합니다.
1. 팝업 창에 “NVIDIA 제어판” 또는 “NVIDIA 디스플레이”가 표시되면 NVIDIA GPU가 있는 것입니다.
1. 팝업 창에서 “NVIDIA 제어판” 또는 “NVIDIA 디스플레이”를 클릭합니다.
1. “그래픽 카드 정보”를 확인합니다.
1. NVIDIA GPU 이름이 표시됩니다.

**NVIDIA 제어판은 표시되지 않지만(또는 열지 못함) NVIDIA GPU가 있는 것을 알고 있습니다.**

1. 디바이스 관리자를 엽니다.
1. 디스플레이 어댑터를 살펴봅니다.
1. GPU에 적합한 [드라이버](https://www.nvidia.com/drivers)를 설치합니다.
