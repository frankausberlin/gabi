# Gabi Voice Project Plan

## Phase 1: Foundation (Current)
- [x] Create repository structure
- [x] Set up GitHub integration
- [ ] Research Whisper implementations for RTX 4060 Ti
- [ ] Research TTS options (ElevenLabs vs local)
- [ ] Design audio pipeline architecture

## Phase 2: Local Whisper Implementation
- [ ] Choose Whisper framework (whisper.cpp vs faster-whisper vs original)
- [ ] Install dependencies (CUDA, PyTorch, etc.)
- [ ] Test audio capture on system
- [ ] Implement basic Whisper transcription
- [ ] Benchmark performance on RTX 4060 Ti

## Phase 3: TTS Integration
- [ ] Select TTS solution (ElevenLabs API vs Piper vs Coqui)
- [ ] Implement text-to-speech pipeline
- [ ] Test voice quality and latency
- [ ] Create voice personality settings

## Phase 4: Real-time Conversation
- [ ] Implement Voice Activity Detection (VAD)
- [ ] Build audio streaming pipeline
- [ ] Create conversation state manager
- [ ] Add "interrupt" (ins Wort fallen) capability
- [ ] Test end-to-end latency

## Phase 5: Integration & Polish
- [ ] Integrate with OpenClaw
- [ ] Create VS Code KiloCode extension
- [ ] Add configuration management
- [ ] Performance optimization
- [ ] Documentation and how-to guides

## Phase 6: Advanced Features
- [ ] Multi-language support
- [ ] Emotion/intonation control
- [ ] Background noise filtering
- [ ] Offline mode optimization
- [ ] Mobile companion app

## Technical Stack Considerations

### Whisper Options:
1. **whisper.cpp** - C++ optimized, good for CPU/GPU, quantized models
2. **faster-whisper** - PyTorch, CUDA support, good GPU utilization
3. **OpenAI Whisper** - Original, slower but reference implementation

### TTS Options:
1. **ElevenLabs** - Best quality, API costs, requires internet
2. **Piper** - Local, open-source, decent quality
3. **Coqui TTS** - Local, customizable, good for research
4. **Edge-TTS** - Free Microsoft voices, requires internet

### Audio Pipeline:
- **Capture**: PyAudio / sounddevice
- **VAD**: Silero VAD / WebRTC VAD
- **Processing**: NumPy, Librosa
- **Playback**: PyAudio / sounddevice