# TensorFlow-Audio-Recognition-Tutorial-Fixed
The code fixed of the example in https://codelabs.developers.google.com/codelabs/tensorflowjs-audio-codelab/index.html
We only need to change this part of the code in Speech-Recognition lines 247 to
'''
                            case 1:
                                //This needs to b changed to our System
                                // this.sampleRateHz = 48000;
                                // this.audioContext = new AudioContext({ sampleRate: this.sampleRateHz });
                                this.audioContext = new AudioContext();
                                this.sampleRateHz = this.audioContext.sampleRate;
                                console.log("Value of sampleRateHz");
                                console.log(this.sampleRateHz);
                                console.log("Value of audioContext");
                                console.log(this.audioContext);
                                // console.log(a.sent());
                                return (
                                    (t.stream = a.sent()),
                                    (this.audioContext),
                                    this.audioContext.sampleRate !== this.sampleRateHz && console.warn("Mismatch in sampling rate: Expected: " + this.sampleRateHz + "; Actual: " + this.audioContext.sampleRate),
                                    (r = this.audioContext.createMediaStreamSource(this.stream)),
                                    (this.analyser = this.audioContext.createAnalyser()),
                                    (this.analyser.fftSize = 2 * this.fftSize),
                                    (this.analyser.smoothingTimeConstant = 0),
                                    r.connect(this.analyser),
                                    (this.freqDataQueue = []),
                                    (this.freqData = new Float32Array(this.fftSize)),
                                    this.includeRawAudio && ((this.timeDataQueue = []), (this.timeData = new Float32Array(this.fftSize))),
                                    (n = Math.max(1, Math.round(this.numFrames * (1 - this.overlapFactor)))),
                                    (this.tracker = new m(n, Math.round(this.suppressionTimeMillis / this.frameDurationMillis))),
                                    (this.frameIntervalTask = setInterval(this.onAudioFrame.bind(this), (this.fftSize / this.sampleRateHz) * 1e3)), [2]
                                );
'''
Have a nice developing jornal, let me know any question, i will put here my project working, so you are free to download and make your own experiments.

