plot_rdm(doppler_axis, range_axis, RDM, 'Range Doppler Map');
CFAR_map = cfar(RDM, 10, 8, 4, 4, 6);
plot_rdm(doppler_axis, range_axis, CFAR_map, 'CFAR Detection');
