# txdy
% [S,alpha,f] = Fast_SC(x,Nw,alpha_max,Fs,opt)
% Fast estimation of the Spectral Correlation based on the Short-Time-Fourier-Transform (STFT).
% (stand-alone Matlab code)
%
% Inputs:
% -------
% x: signal whose spectral correlation is to be computed.
% Nw: window size used in STFT.
% alpha_max: upper bound of the cyclic frequency range to scan (in Hz).
% Fs: sampling frequency in Hz (default = 1Hz).
% opt.coh = 1: the spectral COHERENCE is computed instead of the (default) spectral CORRELATION.
%
% Outputs:
% --------
% S: spectral correlation matrix ; dimension = (positive frequencies)x(cyclic frequencies).
% alpha: vector of cyclic frequencies in Hz.
% f: vector of spectral frequencies in Hz.
% STFT: Short-Time-Fourier-Transform matrix ; dimension = (positive frequencies)x(time instants).
% t: vector of time instants of the STFT (in seconds).
% Nv: number of overlapped samples.
%
% Recommendations for setting the paramaters:
% -------------------------------------------
% 1) Nw sets the frequency resolution df ~ 1.5*Fs/Nw (in Hz). The shorter Nw,
% the faster the algorithm. A power of 2 is recommended so as to make
% possible the use of the FFT.
% 2) alpha_max should be set to the largest cyclic frequency of interest,
% but not larger. The shorter it is, the faster the algorithm.
% 
%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Author: J. Antoni, September 2016
% Reference: 
% J. Antoni, G. Xin, N. Hamzaoui, "Fast Computation of the Spectral Correlation", 
% Mechanical Systems and Signal Processing, Elsevier, 2017.
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
